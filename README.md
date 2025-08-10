<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Elhassan Investment</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background-color: #f4f4f4;
    }
    header {
      background-color: #003366;
      color: white;
      padding: 20px;
      text-align: center;
    }
    nav {
      background-color: #0055a5;
      display: flex;
      justify-content: center;
      padding: 10px;
    }
    nav a {
      color: white;
      margin: 0 15px;
      text-decoration: none;
      font-weight: bold;
    }
    .hero {
      background-color: #e0e0e0;
      padding: 60px 20px;
      text-align: center;
    }
    .hero h1 {
      font-size: 2.5em;
      margin-bottom: 10px;
    }
    .hero p {
      font-size: 1.2em;
      margin-bottom: 20px;
    }
    .cta-button {
      background-color: #003366;
      color: white;
      padding: 12px 25px;
      text-decoration: none;
      border-radius: 5px;
      font-weight: bold;
    }
    .features {
      display: flex;
      justify-content: space-around;
      padding: 40px 20px;
      background-color: white;
    }
    .feature {
      width: 30%;
      text-align: center;
    }
    footer {
      background-color: #003366;
      color: white;
      text-align: center;
      padding: 20px;
    }
  </style>
</head>
<body>

  <header>
    <h1>Elhassan Investment</h1>
    <p>Empowering Growth Through Strategic Investment</p>
  </header>

  <nav>
    <a href="#">Home</a>
    <a href="#">About Us</a>
    <a href="#">Services</a>
    <a href="#">Portfolio</a>
    <a href="#">Contact</a>
  </nav>

  <section class="hero">
    <h1>Welcome to Elhassan Investment</h1>
    <p>Trusted by SMEs, entrepreneurs, and communities across Nigeria.</p>
    <a href="#" class="cta-button">Get Started</a>
  </section>

  <section class="features">
    <div class="feature">
      <h3>SMEDAN Registered</h3>
      <p>Officially recognized and compliant with Nigerian standards.</p>
    </div>
    <div class="feature">
      <h3>Experienced Team</h3>
      <p>Years of expertise in investment and business development.</p>
    </div>
    <div class="feature">
      <h3>Sector Diversity</h3>
      <p>Real Estate, Agriculture, Startups, and more.</p>
    </div>
  </section>

  <footer>
    <p>&copy; 2025 Elhassan Investment. All rights reserved.</p>
  </footer>

</body>
</html>
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
