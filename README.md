#LumozQuidditchBot 



https://github.com/user-attachments/assets/c6542980-32ed-4086-b70c-0a90dfa3611e


### فارسی (Persian)

# 🛠 نحوه استفاده:

1. 🌐 ابتدا وارد نسخه [a تلگرام](https://web.telegram.org/a) شوید.
2. 🤖 با این [لینک](https://t.me/Lumoz_Quidditch_Bot/Match?startapp=inviteBHLGX) وارد ربات لوموز شوید.
3. 🕹 بعد از زدن دکمه "play"، روی وسط صفحه‌ی بازی راست کلیک کنید و گزینه‌ی "Inspect" را بزنید.
4. 🖥 وارد بخش "Console" شوید.
5. 📋 کد زیر را کپی کنید و در کنسول پیست کرده و اینتر را بزنید!

---

### English

# 🛠 How to use:

1. 🌐 First, go to the [Telegram Web version a](https://web.telegram.org/a).
2. 🤖 Enter the Lumoz bot using this [link](https://t.me/Lumoz_Quidditch_Bot/Match?startapp=inviteBHLGX).
3. 🕹 After pressing "play", right-click in the middle of the game screen and select "Inspect".
4. 🖥 Go to the "Console" section.
5. 📋 Copy the code below, paste it into the console, and hit Enter!




```
const clickedElements = new Set();

function simulateClick(element) {
    const event = new MouseEvent('click', {
        view: window,
        bubbles: true,
        cancelable: true
    });
    element.dispatchEvent(event);
}

function clickOnNewElements() {
    const elements = document.querySelectorAll('div.relative.animated-button.w-13.h-13.blink');
    
    elements.forEach(element => {
        if (!clickedElements.has(element.id)) {
            console.log(`Found new element with ID: ${element.id}`);
            
            const imgElement = element.querySelector('img.w-13.h-13');
            const textElement = element.querySelector('div.text-xs.-mt-2.text-\\[\\#D6C2A2\\].bg-\\[\\#512A1980\\].rounded-full.text-center.w-10.absolute.h-4');
            
            if (imgElement && textElement) {
                console.log(`Attempting to click element with ID: ${element.id}`);
                simulateClick(element);
                clickedElements.add(element.id);
                console.log(`Clicked element with ID: ${element.id}`);
                setTimeout(() => {
                    clickedElements.delete(element.id);
                    console.log(`Removed element with ID: ${element.id} from clickedElements set.`);
                }, 300000);
            } else {
                console.log(`Element with ID ${element.id} doesn't have expected structure. Skipping.`);
            }
        }
    });
}
const observer = new MutationObserver(mutations => {
    console.log('Detected DOM mutations, checking for new elements...');
    clickOnNewElements();
});
const config = { childList: true, subtree: true };
observer.observe(document.body, config);
console.log('Script starting with MutationObserver...');
clickOnNewElements();
```

