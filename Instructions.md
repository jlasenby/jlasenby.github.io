   Site Structure:                                                               - Brutalist/minimalist design (black background, neon green links,          
  monospaced fonts)                                                           
  - Home page with recent posts
  - Blog archive page
  - About page
  - Now page
  - Sample welcome post
  - Custom domain configuration (CNAME file)

  Repository:
  - Location: C:\Users\James\Documents\GitHub\Lasenby.com
  - GitHub: https://github.com/jlasenby/jlasenby.github.io
  - Initial deployment: Live at https://jlasenby.github.io

  🔧 Next Steps: DNS Configuration

  To make your site accessible at lasenby.com, configure these DNS records at 
  your domain registrar:

  A Records (for apex domain):
  Type: A
  Name: @
  Value: 185.199.108.153

  Type: A
  Name: @
  Value: 185.199.109.153

  Type: A
  Name: @
  Value: 185.199.110.153

  Type: A
  Name: @
  Value: 185.199.111.153

  CNAME Record (for www subdomain):
  Type: CNAME
  Name: www
  Value: jlasenby.github.io

  After DNS configuration:
  1. Wait 24-48 hours for DNS propagation
  2. Go to: https://github.com/jlasenby/jlasenby.github.io/settings/pages     
  3. Verify "Custom domain" shows: lasenby.com
  4. Check "Enforce HTTPS" once DNS verifies

  📝 Using Obsidian

  To edit your site in Obsidian:

  1. Open Obsidian → "Open folder as vault"
  2. Select: C:\Users\James\Documents\GitHub\Lasenby.com
  3. Go to Settings → Files & Links:
    - Turn OFF "Use [[Wikilinks]]"
    - Set attachment folder to: assets/images
  4. Create posts in _posts/ with format: YYYY-MM-DD-title.md

  Your site is ready to use!