# Create a directory for the website files
site_dir = '/mnt/data/elhassan_investment_site'
os.makedirs(site_dir, exist_ok=True)

# HTML content from the updated website
html_content = """<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Elhassan Investment</title>
  <meta name="description" content="Elhassan Investment — trusted financial and investment services.">
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    :root{
      --green: #1f8a4c;
      --gold: #cfa34b;
    }
  </style>
</head>
<body class="antialiased text-gray-800 bg-gray-50">
  <header class="bg-white shadow-sm">
    <div class="max-w-6xl mx-auto px-6 py-4 flex items-center justify-between">
      <a href="#home" class="flex items-center gap-3">
        <img src="1000181877.png" alt="Elhassan Investment Logo" class="h-12">
        <div>
          <h1 class="text-lg font-semibold">Elhassan Investment</h1>
          <p class="text-xs text-gray-500">Trusted • Growth • Integrity</p>
        </div>
      </a>
      <nav class="hidden md:flex items-center gap-6 text-sm">
        <a href="#about" class="hover:text-[var(--green)]">About</a>
        <a href="#services" class="hover:text-[var(--green)]">Services</a>
        <a href="#certificate" class="hover:text-[var(--green)]">Certificate</a>
        <a href="#contact" class="hover:text-[var(--green)]">Contact</a>
      </nav>
    </div>
  </header>

  <main id="home" class="mt-10">
    <section class="max-w-6xl mx-auto px-6 grid md:grid-cols-2 gap-12 items-center">
      <div>
        <h2 class="text-4xl font-extrabold leading-tight">Elhassan Investment</h2>
        <p class="mt-4 text-lg text-gray-700">We provide trusted investment and financial advisory services focused on sustainable growth for individuals and small businesses in Zaria, Kaduna, Nigeria.</p>
        <div class="mt-6 flex gap-4">
          <a href="#contact" class="bg-[var(--green)] text-white px-5 py-3 rounded-md shadow">Get Started</a>
          <a href="#certificate" class="border border-gray-300 px-5 py-3 rounded-md">View Certificate</a>
        </div>
      </div>
      <div>
        <img src="1000181877.png" alt="Elhassan Investment Logo" class="rounded-xl shadow-lg">
      </div>
    </section>

    <section id="contact" class="mt-12 max-w-6xl mx-auto px-6 mb-20">
      <div class="bg-white rounded-lg p-8 shadow-sm">
        <h3 class="text-xl font-bold">Contact Us</h3>
        <p class="text-gray-600 mt-2">Send us a message and we'll get back to you.</p>
        <p class="mt-4 text-gray-800 font-medium">Email: <a href="mailto:elhassy74@gmail.com" class="text-[var(--green)]">elhassy74@gmail.com</a></p>
        <p class="text-gray-800 font-medium">Location: Zaria, Kaduna, Nigeria</p>
      </div>
    </section>
  </main>

  <footer class="bg-white border-t py-6">
    <div class="max-w-6xl mx-auto px-6 flex flex-col sm:flex-row items-center justify-between text-sm text-gray-600">
      <div>© <span id="year"></span> Elhassan Investment. All rights reserved.</div>
      <div>SMEDAN: SUIN16895651</div>
    </div>
  </footer>

  <script>
    document.getElementById('year').textContent = new Date().getFullYear();
  </script>
</body>
</html>
"""

# Save HTML file
html_file_path = os.path.join(site_dir, 'index.html')
with open(html_file_path, 'w', encoding='utf-8') as f:
    f.write(html_content)

# Copy the logo image to the site folder
import shutil
shutil.copy('/mnt/data/1000181877.png', os.path.join(site_dir, '1000181877.png'))

# Create ZIP archive
zip_path = '/mnt/data/elhassan_investment_site.zip'
with ZipFile(zip_path, 'w') as zipf:
    for root, dirs, files in os.walk(site_dir):
        for file in files:
            zipf.write(os.path.join(root, file), arcname=file)

zip_path
