<template>
  <section id="order" class="section-pad relative overflow-hidden" style="background: #F8F9FA;">
    <div style="position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,transparent,#C9A84C,transparent);"></div>

    <div class="max-w-2xl mx-auto px-4 sm:px-6 relative z-10">
      <div class="text-center mb-12 form-header gsap-fade-up">
        <span class="section-tag">📦 اطلب الآن</span>
        <h2 class="section-title mt-3 mb-3">احجز طلبك الآن</h2>
        <div class="gold-divider"></div>
        <p class="section-subtitle mx-auto mt-5">اطلب الآن والتوصيل لحد بابك خلال 48 ساعة</p>

        <div class="mt-6 flex flex-col sm:flex-row gap-3 justify-center items-center">
          <a href="https://wa.me/201551866195?text=مرحباً،%20أريد%20الطلب%20من%20سينا%20جولد"
            target="_blank" rel="noopener" class="btn-wa w-full sm:w-auto">
            <svg class="w-5 h-5 flex-shrink-0" fill="currentColor" viewBox="0 0 24 24">
              <path d="M12.031 6.172c-3.181 0-5.767 2.586-5.768 5.766-.001 1.298.38 2.27 1.019 3.287l-.582 2.128 2.182-.573c.978.58 1.911.928 3.145.929 3.178 0 5.767-2.587 5.768-5.766.001-3.187-2.575-5.77-5.764-5.771zm3.392 8.244c-.144.405-.837.774-1.17.824-.299.045-.677.063-1.092-.125-.339-.153-.889-.356-1.785-.886-1.139-.672-1.89-1.802-1.947-1.879-.057-.077-.464-.618-.464-1.178 0-.56.289-.838.391-.947.102-.109.222-.136.297-.136l.214.004c.068.004.156-.027.244.184l.328.792c.027.054.045.118.012.191-.034.073-.051.118-.102.219-.051.101-.107.219-.153.272-.051.063-.105.129-.044.234.061.105.274.453.586.733.404.362.748.475.857.531.109.056.173.045.237-.027.064-.073.277-.323.352-.434.075-.111.149-.092.245-.056l.713.339c.105.051.175.077.201.12.026.043.026.25-.118.655z"/>
            </svg>
            اطلب عبر واتساب الآن
          </a>
          <div style="color:#9AAD92;font-size:0.8rem;font-weight:600;">أو</div>
          <a href="mailto:mohamediibrahim785@gmail.com?subject=طلب زيت سينا جولد"
            class="btn-olive-outline text-sm px-5 py-2.5 w-full sm:w-auto justify-center">
            📧 التواصل بالإيميل
          </a>
        </div>

        <div class="mt-4 inline-flex items-center gap-2 px-4 py-1.5 rounded-full"
          style="background:rgba(16,185,129,0.06);border:1px solid rgba(16,185,129,0.18);">
          <span class="w-2 h-2 bg-green-500 rounded-full" style="animation:pulse 1.5s infinite;"></span>
          <span style="color:#059669;font-size:0.8rem;font-weight:700;">الدفع عند الاستلام 100%</span>
        </div>
      </div>

      <div class="flex items-center gap-4 mb-8">
        <div class="flex-grow h-px" style="background:rgba(0,0,0,0.08);"></div>
        <span style="color:#9AAD92;font-size:0.8rem;font-weight:600;">أو أرسل طلبك بالنموذج</span>
        <div class="flex-grow h-px" style="background:rgba(0,0,0,0.08);"></div>
      </div>

      <div class="form-card gsap-scale-in white-card p-8 md:p-10 relative overflow-hidden">
        <div style="position:absolute;top:0;left:0;right:0;height:3px;background:linear-gradient(90deg,#C9A84C,#3D7A1E);"></div>

        <form @submit.prevent="submitForm" ref="formEl" class="space-y-5" novalidate>
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-5">
            <div>
              <label class="form-lbl">الاسم الكامل *</label>
              <input v-model="form.name" name="user_name" type="text" required
                class="dark-input" :class="errors.name ? 'error-input' : ''"
                placeholder="اكتب اسمك ثلاثي" @blur="v('name')" />
              <p v-if="errors.name" class="err-msg">{{ errors.name }}</p>
            </div>
            <div>
              <label class="form-lbl">رقم الموبايل *</label>
              <input v-model="form.phone" name="user_phone" type="tel" required dir="ltr"
                class="dark-input text-right" :class="errors.phone ? 'error-input' : ''"
                placeholder="01xxxxxxxxx" @blur="v('phone')" />
              <p v-if="errors.phone" class="err-msg">{{ errors.phone }}</p>
            </div>
          </div>

          <div>
            <label class="form-lbl">العنوان بالتفصيل *</label>
            <input v-model="form.address" name="user_address" type="text" required
              class="dark-input" :class="errors.address ? 'error-input' : ''"
              placeholder="المحافظة، المركز، الشارع، رقم المبنى" @blur="v('address')" />
            <p v-if="errors.address" class="err-msg">{{ errors.address }}</p>
          </div>

          <div>
            <label class="form-lbl">اختر المنتج *</label>
            <div class="grid grid-cols-3 gap-3">
              <div v-for="opt in productOpts" :key="opt.value"
                @click="form.product = opt.value"
                class="product-opt rounded-xl p-3 text-center cursor-pointer transition-all duration-200"
                :class="form.product === opt.value ? 'opt-active' : 'opt-idle'">
                <div style="font-size:1.4rem;margin-bottom:4px;">{{ opt.icon }}</div>
                <div style="font-size:0.75rem;font-weight:700;color:#0F1A0A;line-height:1.2;">{{ opt.label }}</div>
                <div style="font-size:0.72rem;font-weight:800;color:#C9A84C;margin-top:3px;">{{ opt.price }} ج</div>
              </div>
            </div>
          </div>

          <input type="hidden" name="product" :value="form.product" />

          <div>
            <label class="form-lbl">ملاحظات إضافية</label>
            <textarea v-model="form.message" name="message" rows="3"
              class="dark-input resize-none"
              placeholder="أي طلبات خاصة أو تعليمات للتوصيل..."></textarea>
          </div>

          <button type="submit" :disabled="isSubmitting"
            class="btn-gold w-full py-4 text-lg rounded-2xl flex items-center justify-center gap-3"
            :style="isSubmitting ? 'opacity:0.65;cursor:not-allowed;' : ''">
            <svg v-if="isSubmitting" class="animate-spin w-5 h-5" fill="none" viewBox="0 0 24 24">
              <circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle>
              <path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4z"></path>
            </svg>
            <span>{{ isSubmitting ? 'جاري الإرسال...' : '✅ تأكيد الطلب ' }}</span>
          </button>

          <p style="text-align:center;font-size:0.75rem;color:#9AAD92;">
            🔒 بياناتك آمنة — لن نشاركها مع أي جهة
          </p>
        </form>

        <Transition name="fade-overlay">
          <div v-if="showSuccess"
            style="position:absolute;inset:0;background:rgba(255,255,255,0.97);backdrop-filter:blur(8px);display:flex;flex-direction:column;align-items:center;justify-content:center;text-align:center;padding:2rem;border-radius:1.25rem;z-index:20;">
            <div class="success-check" style="width:80px;height:80px;background:linear-gradient(135deg,#1a7a42,#25D366);border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:2.5rem;color:#fff;box-shadow:0 0 40px rgba(37,211,102,0.25);margin-bottom:1.5rem;">
              ✓
            </div>
            <h3 style="font-size:1.6rem;font-weight:900;color:#0F1A0A;margin-bottom:0.5rem;">تم استلام طلبك! 🎉</h3>
            <p style="color:#6B7E64;font-size:1rem;margin-bottom:0.5rem;">هنتواصل معاك خلال ساعات لتأكيد الشحن.</p>
            <p style="color:#C9A84C;font-weight:700;font-size:0.9rem;">التوصيل لحد بابك خلال 48 ساعة 🚚</p>
            <button @click="resetForm" class="btn-gold mt-8 px-8 py-3 rounded-full">تقديم طلب آخر</button>
          </div>
        </Transition>
      </div>

      <div class="mt-8 grid grid-cols-3 gap-4 form-trust gsap-fade-up">
        <div v-for="t in trustBadges" :key="t.label" class="white-card p-4 flex flex-col items-center text-center gap-2">
          <div style="font-size:1.5rem;">{{ t.icon }}</div>
          <p style="font-size:0.72rem;font-weight:700;color:#6B7E64;line-height:1.3;">{{ t.label }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';
import emailjs from '@emailjs/browser';
gsap.registerPlugin(ScrollTrigger);

const formEl = ref(null);
const isSubmitting = ref(false);
const showSuccess = ref(false);
const form = ref({ name:'', phone:'', address:'', product:'750ml', message:'' });
const errors = ref({ name:'', phone:'', address:'' });

const productOpts = [
  { value:'500ml', icon:'🫙', label:'500 مل', price:'300' },
  { value:'1L',    icon:'🍶', label:'1 لتر',  price:'580' },
  { value:'pack3', icon:'📦', label:'3 لتر',  price:'1700' },
];
const trustBadges = [
  { icon:'🚚', label:'توصيل لكل المحافظات' },
  { icon:'💳', label:'مش هنختلف علي الدفع يحج' },
  { icon:'↩️', label:'ضمان جودة أو استرداد' },
];

const v = (f) => {
  if (f==='name')    errors.value.name    = form.value.name.trim().length<3    ? 'الاسم يجب أن يكون 3 أحرف على الأقل' : '';
  if (f==='phone')   errors.value.phone   = !/^01[0-9]{9}$/.test(form.value.phone.trim()) ? 'رقم موبايل مصري صحيح (11 رقم)' : '';
  if (f==='address') errors.value.address = form.value.address.trim().length<10 ? 'أدخل العنوان بالتفصيل' : '';
};
const vAll = () => { v('name');v('phone');v('address'); return !errors.value.name && !errors.value.phone && !errors.value.address; };

const submitForm = async () => {
  if (!vAll()) {
    gsap.to('.form-card', { keyframes:[{x:-8},{x:8},{x:-6},{x:6},{x:0}], duration:0.4, ease:'power2.inOut' });
    return;
  }
  isSubmitting.value = true;
  try {
    await emailjs.sendForm('service_wdlai8p', 'template_qrlaqpo', formEl.value, 'lrMoNQeNkdaU1dFCo');
    showSuccess.value = true;
    setTimeout(() => {
      gsap.fromTo('.success-check', {scale:0,rotation:-180}, {scale:1,rotation:0,duration:0.6,ease:'back.out(1.7)'});
    }, 60);
  } catch(e) {
    console.error(e);
    alert('حدث خطأ. تواصل معنا عبر واتساب مباشرةً.');
  } finally { isSubmitting.value = false; }
};
const resetForm = () => {
  form.value = {name:'',phone:'',address:'',product:'750ml',message:''};
  errors.value = {name:'',phone:'',address:''};
  showSuccess.value = false;
};

onMounted(() => {
  gsap.to('.form-header', { scrollTrigger:{trigger:'.form-header',start:'top 85%'}, y:0,opacity:1,duration:0.8,ease:'power3.out' });
  gsap.to('.form-card',   { scrollTrigger:{trigger:'.form-card',  start:'top 85%'}, scale:1,opacity:1,duration:0.8,ease:'back.out(1.2)' });
  gsap.to('.form-trust',  { scrollTrigger:{trigger:'.form-trust', start:'top 90%'}, y:0,opacity:1,duration:0.6,delay:0.3 });
});
</script>

<style scoped>
.form-lbl { display:block; font-size:0.82rem; font-weight:700; color:#6B7E64; margin-bottom:0.35rem; }
.err-msg  { color:#dc2626; font-size:0.76rem; font-weight:600; margin-top:0.25rem; }
.error-input { border-color: rgba(220,38,38,0.5) !important; }

.opt-idle   { background: #F8F9FA; border: 1.5px solid rgba(0,0,0,0.10); }
.opt-idle:hover { border-color: rgba(201,168,76,0.35); background: #FFFFFF; }
.opt-active { background: rgba(201,168,76,0.07); border: 1.5px solid rgba(201,168,76,0.45); box-shadow: 0 0 15px rgba(201,168,76,0.10); }

.fade-overlay-enter-active, .fade-overlay-leave-active { transition: opacity 0.4s ease; }
.fade-overlay-enter-from, .fade-overlay-leave-to { opacity: 0; }
</style>