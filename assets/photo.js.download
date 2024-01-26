const image = document.querySelector('.photo img');
const fileInput = document.createElement('input');
fileInput.type = 'file';
fileInput.accept = 'image/*';

fileInput.addEventListener('change', function() {
  const file = fileInput.files[0];

  const reader = new FileReader();

  reader.addEventListener('load', function() {
    image.src = reader.result;

    // Create a new canvas element
    const canvas = document.createElement('canvas');
    canvas.width = image.width;
    canvas.height = image.height;

    // Get the canvas context
    const context = canvas.getContext('2d');

    // Draw the image element onto the canvas context
    context.drawImage(image, 0, 0);

    // Get the image data from the canvas context
    const imageData = canvas.toDataURL();

    // Embed the image data in the PDF
    pdf.addImage(imageData, 0, 0);
  });

  reader.readAsDataURL(file);
});

image.addEventListener('click', function() {
  fileInput.click();
});
