<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "b6897c02603d0045dd6d8256e8714baa",
  "translation_date": "2025-10-24T17:05:11+00:00",
  "source_file": "5-browser-extension/1-about-browsers/assignment.md",
  "language_code": "my"
}
-->
# အလုပ်ပေးချက်: သင့် Browser Extension ကို Restyle လုပ်ပါ

## အကျဉ်းချုပ်

သင့် carbon footprint browser extension အတွက် HTML ဖွဲ့စည်းမှုကို တည်ဆောက်ပြီးသားဖြစ်သောကြောင့်၊ ယခုအခါမှာ သင့် extension ကို အလှပဆုံးဖြစ်စေပြီး အသုံးပြုသူများအတွက် အဆင်ပြေစေဖို့ အရေးကြီးပါသည်။ အလှပသော ဒီဇိုင်းသည် အသုံးပြုသူအတွေ့အကြုံကို မြှင့်တင်ပေးပြီး သင့် extension ကို ပရော်ဖက်ရှင်နယ်နှင့် စိတ်ဝင်စားဖွယ်ဖြစ်စေပါသည်။

သင့် extension တွင် အခြေခံ CSS အလှဆင်မှုများပါဝင်ပြီးသားဖြစ်သော်လည်း၊ ဒီအလုပ်ပေးချက်သည် သင့်ကို သင့်ကိုယ်ပိုင်စတိုင်ကို ဖော်ပြနိုင်သော ထူးခြားသော visual identity တစ်ခုကို ဖန်တီးရန် စိန်ခေါ်ပါသည်။ 

## လမ်းညွှန်ချက်များ

### အပိုင်း ၁: လက်ရှိဒီဇိုင်းကို ခွဲခြမ်းစိတ်ဖြာပါ

ပြုပြင်မှုများလုပ်မီ၊ လက်ရှိ CSS ဖွဲ့စည်းမှုကို စိစစ်ပါ:

1. **CSS ဖိုင်များ** ကို သင့် extension project မှာ ရှာဖွေပါ
2. **လက်ရှိအလှဆင်မှုနည်းလမ်း** နှင့် အရောင်စနစ်ကို ပြန်လည်သုံးသပ်ပါ
3. **တိုးတက်မှုအတွက် အပိုင်းများ** ကို layout, typography, visual hierarchy အပိုင်းများတွင် ရှာဖွေပါ
4. **ဒီဇိုင်းသည် အသုံးပြုသူရည်ရွယ်ချက်များကို ဘယ်လိုထောက်ပံ့ပေးနိုင်သည်ကို** စဉ်းစားပါ (form ဖြည့်ခြင်းနှင့် အချက်အလက်ပြသမှုကို လွယ်ကူစေခြင်း)

### အပိုင်း ၂: သင့်ကိုယ်ပိုင်အလှဆင်မှုဒီဇိုင်းကို ဖန်တီးပါ

အလှဆင်မှုဒီဇိုင်းတစ်ခုကို ဖန်တီးပါ:

**အရောင်စနစ်:**
- ပတ်ဝန်းကျင်ဆိုင်ရာအဓိကအရောင် palette ကို ရွေးချယ်ပါ
- Accessibility အတွက် contrast လုံလောက်မှုရှိစေရန် သေချာပါ (WebAIM's contrast checker ကိရိယာများကို အသုံးပြုပါ)
- အရောင်များသည် browser themes များအပေါ် ဘယ်လိုပုံပေါ်မည်ကို စဉ်းစားပါ

**Typography:**
- Extension အရွယ်အစားသေးငယ်များတွင် အလွယ်တကူဖတ်နိုင်သော font များကို ရွေးချယ်ပါ
- Font size နှင့် weight များကို သင့်တော်သော hierarchy ဖြင့် သတ်မှတ်ပါ
- Text များသည် light နှင့် dark browser themes နှစ်ခုစလုံးတွင် ဖတ်နိုင်စေရန် သေချာပါ

**Layout နှင့် Spacing:**
- Form elements နှင့် data display များ၏ visual organization ကို တိုးတက်စေပါ
- ဖတ်ရှုရလွယ်ကူစေရန် padding နှင့် margin များကို ထည့်သွင်းပါ
- Responsive design principles များကို screen size များအလိုက် စဉ်းစားပါ

### အပိုင်း ၃: သင့်ဒီဇိုင်းကို အကောင်အထည်ဖော်ပါ

CSS ဖိုင်များကို ပြုပြင်ပြီး သင့်ဒီဇိုင်းကို အကောင်အထည်ဖော်ပါ:

```css
/* Example starting points for customization */

.form-data {
    /* Style the configuration form */
    background: /* your choice */;
    padding: /* your spacing */;
    border-radius: /* your preference */;
}

.result-container {
    /* Style the data display area */
    background: /* complementary color */;
    border: /* your border style */;
    margin: /* your spacing */;
}

/* Add your custom styles here */
```

**အဓိကအလှဆင်ရန်နေရာများ:**
- **Form elements**: Input fields, labels, နှင့် submit button
- **Results display**: Data container, text styling, နှင့် loading states
- **Interactive elements**: Hover effects, button states, နှင့် transitions
- **Overall layout**: Container spacing, background colors, နှင့် visual hierarchy

### အပိုင်း ၄: စမ်းသပ်ပြီး ပြုပြင်ပါ

1. **npm run build** ဖြင့် သင့် extension ကို build လုပ်ပါ
2. **Updated extension** ကို သင့် browser တွင် load လုပ်ပါ
3. **Visual states အားလုံး** (form entry, loading, results display, errors) ကို စမ်းသပ်ပါ
4. **Browser developer tools** ဖြင့် accessibility ကို စစ်ဆေးပါ
5. **အသုံးပြုမှုအပေါ် အခြေခံပြီး သင့် styles ကို ပြုပြင်ပါ**

## ဖန်တီးမှုစိန်ခေါ်မှုများ

### အခြေခံအဆင့်
- အရောင်နှင့် font များကို update လုပ်ပြီး cohesive theme တစ်ခုကို ဖန်တီးပါ
- Interface တစ်ခုလုံးတွင် spacing နှင့် alignment ကို တိုးတက်စေပါ
- Interactive elements များတွင် subtle hover effects ထည့်သွင်းပါ

### အလယ်အဆင့်
- သင့် extension အတွက် custom icons သို့မဟုတ် graphics များကို ဒီဇိုင်းဆွဲပါ
- အခြေအနေများအကြား smooth transitions များကို အကောင်အထည်ဖော်ပါ
- API calls အတွက် ထူးခြားသော loading animation တစ်ခုကို ဖန်တီးပါ

### အဆင့်မြင့်
- အမျိုးမျိုးသော theme ရွေးချယ်မှုများ (light/dark/high-contrast) ကို ဒီဇိုင်းဆွဲပါ
- Browser window size များအတွက် responsive design ကို အကောင်အထည်ဖော်ပါ
- အသုံးပြုသူအတွေ့အကြုံကို မြှင့်တင်ပေးသော micro-interactions များကို ထည့်သွင်းပါ

## အလုပ်ပေးချက်တင်သွင်းရန် လမ်းညွှန်ချက်များ

သင့်ပြီးစီးသောအလုပ်ပေးချက်တွင် ပါဝင်ရမည့်အရာများ:

- **Modified CSS files** သင့် custom styling ဖြင့်
- **Screenshots** သင့် extension ၏ အခြေအနေများ (form, loading, results) ကို ပြသထားသော
- **Design choices** နှင့် အသုံးပြုသူအတွေ့အကြုံကို ဘယ်လိုတိုးတက်စေသည်ကို ရှင်းလင်းသော အကြောင်းအရာ (၂-၃ စာကြောင်း)

## အကဲဖြတ်မှုအခြေခံချက်

| အချက်အလက် | ထူးချွန်မှု (4) | ကျွမ်းကျင်မှု (3) | တိုးတက်မှု (2) | အခြေခံ (1) |
|------------|------------------|-------------------|----------------|-------------|
| **Visual Design** | အသုံးပြုမှုကို မြှင့်တင်ပေးသော ထူးခြားပြီး cohesive ဒီဇိုင်း | ဒီဇိုင်းရွေးချယ်မှုကောင်းများနှင့် visual hierarchy ရှင်းလင်းမှု | အခြေခံဒီဇိုင်းတိုးတက်မှုများ | Styling ပြုပြင်မှုနည်းပါးခြင်း |
| **Functionality** | အခြေအနေများနှင့် browser ပတ်ဝန်းကျင်များအတွက် styles အားလုံးအလုပ်လုပ်ခြင်း | အနည်းငယ်သော edge case ပြဿနာများနှင့် styles အလုပ်လုပ်ခြင်း | Display ပြဿနာအချို့ရှိသော်လည်း styles အများစုအလုပ်လုပ်ခြင်း | Usability ကို ထိခိုက်စေသော styling ပြဿနာများ |
| **Code Quality** | CSS သန့်ရှင်းပြီး class names နှင့် selectors များကို ထိရောက်စွာ အသုံးပြုထားခြင်း | CSS ဖွဲ့စည်းမှုကောင်းပြီး selectors နှင့် properties ကို သင့်တော်စွာ အသုံးပြုထားခြင်း | CSS ဖွဲ့စည်းမှုလုံလောက်မှုရှိခြင်း | CSS ဖွဲ့စည်းမှုမကောင်းခြင်း သို့မဟုတ် အလွန်ရှုပ်ထွေးသော styling |
| **Accessibility** | အရောင် contrast ကောင်းမွန်မှု၊ ဖတ်ရှုရလွယ်ကူသော fonts နှင့် မသန်စွမ်းသူများအတွက် စဉ်းစားထားခြင်း | Accessibility အလေ့အကျင့်ကောင်းများနှင့် အနည်းငယ်သော တိုးတက်မှုလိုအပ်မှုများ | Accessibility အခြေခံအချက်များကို စဉ်းစားထားခြင်း | Accessibility လိုအပ်ချက်များကို အနည်းငယ်သာ စဉ်းစားထားခြင်း |

## အောင်မြင်မှုအတွက် အကြံပြုချက်များ

> 💡 **ဒီဇိုင်းအကြံပြုချက်**: သေးငယ်သောပြုပြင်မှုများဖြင့် စတင်ပြီး အလှဆင်မှုများကို တဖြည်းဖြည်း တိုးတက်စေပါ။ Typography နှင့် spacing အပိုင်းများတွင် သေးငယ်သောတိုးတက်မှုများသည် အရည်အသွေးကို အလွန်တိုးတက်စေပါသည်။

**လိုက်နာရန် အကောင်းဆုံးအလေ့အကျင့်များ:**
- **Test** သင့် extension ကို light နှင့် dark browser themes နှစ်ခုစလုံးတွင်
- **Use** relative units (em, rem) ကို အသုံးပြု၍ scalability ကို မြှင့်တင်ပါ
- **Maintain** CSS custom properties ကို အသုံးပြု၍ spacing ကို တိကျစွာ ထိန်းသိမ်းပါ
- **Consider** သင့်ဒီဇိုင်းသည် visual needs မတူညီသော အသုံးပြုသူများအတွက် ဘယ်လိုပုံပေါ်မည်ကို
- **Validate** သင့် CSS ကို syntax မှန်ကန်မှုရှိစေရန် စစ်ဆေးပါ

> ⚠️ **အများဆုံးဖြစ်သောအမှား**: Visual appeal အတွက် usability ကို မပျက်စီးစေပါနှင့်။ သင့် extension သည် လှပပြီး အသုံးပြုနိုင်ရမည်။

**သတိပြုရန်:**
- **Keep** အရေးကြီးသောအချက်အလက်များကို ဖတ်ရှုရလွယ်ကူစေရန်
- **Ensure** buttons နှင့် interactive elements များကို အလွယ်တကူ click လုပ်နိုင်စေရန်
- **Maintain** အသုံးပြုသူလုပ်ဆောင်မှုများအတွက် visual feedback ရှင်းလင်းမှု
- **Test** သင့်ဒီဇိုင်းကို placeholder text မဟုတ်သော အချက်အလက်များဖြင့် စမ်းသပ်ပါ

သင့် browser extension ကို functional ဖြစ်ပြီး visually stunning ဖြစ်စေရန် အောင်မြင်ပါစေ!

---

**အကြောင်းကြားချက်**:  
ဤစာရွက်စာတမ်းကို AI ဘာသာပြန်ဝန်ဆောင်မှု [Co-op Translator](https://github.com/Azure/co-op-translator) ကို အသုံးပြု၍ ဘာသာပြန်ထားပါသည်။ ကျွန်ုပ်တို့သည် တိကျမှုအတွက် ကြိုးစားနေသော်လည်း အလိုအလျောက် ဘာသာပြန်မှုများတွင် အမှားများ သို့မဟုတ် မမှန်ကန်မှုများ ပါဝင်နိုင်သည်ကို သတိပြုပါ။ မူရင်းဘာသာစကားဖြင့် ရေးသားထားသော စာရွက်စာတမ်းကို အာဏာတရားရှိသော အရင်းအမြစ်အဖြစ် သတ်မှတ်သင့်ပါသည်။ အရေးကြီးသော အချက်အလက်များအတွက် လူ့ဘာသာပြန်ပညာရှင်များကို အသုံးပြုရန် အကြံပြုပါသည်။ ဤဘာသာပြန်မှုကို အသုံးပြုခြင်းမှ ဖြစ်ပေါ်လာသော အလွဲအမှားများ သို့မဟုတ် အနားလွဲမှုများအတွက် ကျွန်ုပ်တို့သည် တာဝန်မယူပါ။