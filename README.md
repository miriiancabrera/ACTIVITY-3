// 1. Open an about:blank page in a new window/tab (size 200x100px)
let blankWindow = window.open('', '', 'width=200,height=100');
debugger; // Pausa aquí

// 2. Open a new window called "MsgWindow" and write "some text"
let msgWindow1 = window.open('', 'MsgWindow', '');
msgWindow1.document.write('some text');
debugger; // Pausa aquí

// 3. Open a new window called "MsgWindow" again and write "some other text"
let msgWindow2 = window.open('', 'MsgWindow', '');
msgWindow2.document.write('some other text');
debugger; // Pausa aquí

// 4. Replace the current window with a new window
window.location.href = 'https://www.example.com'; // Cambia la URL
debugger; // Pausa aquí

// 5. Open a new window and control its appearance
let customWindow = window.open('', '', 'toolbar=yes,scrollbars=yes,resizable=yes,width=200,height=400,left=200,top=100');
debugger; // Pausa aquí

// 6. Open a new window and close it afterwards
let temporaryWindow = window.open('', '', '');
temporaryWindow.close();
debugger; // Pausa aquí

// 7. Using the opener property
let openerWindow = window.open('', '', '');
openerWindow.opener.document.write('some window text');
debugger; // Pausa aquí

// 8. Create an iframe, load iframe.html and write "some text" into it
let iframe = document.createElement('iframe');
iframe.src = 'iframe.html'; // Asegúrate de que el archivo existe
document.body.appendChild(iframe);
iframe.onload = function() {
    let iframeDoc = iframe.contentDocument || iframe.contentWindow.document;
    iframeDoc.write('some text');
};
debugger; // Pausa aquí

// 9. Create an iframe, load iframe.html into it, access its content and print it in this window
let anotherIframe = document.createElement('iframe');
anotherIframe.src = 'iframe.html'; // Cargar contenido
document.body.appendChild(anotherIframe);
anotherIframe.onload = function() {
    let iframeContent = anotherIframe.contentDocument || anotherIframe.contentWindow.document;
    console.log(iframeContent.body.innerHTML); // Imprimir contenido
};
debugger; // Pausa aquí
