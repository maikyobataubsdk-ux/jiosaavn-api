# JioSaavn API

![GitHub License](https://img.shields.io/github/license/sumitkolhe/jiosaavn-api)
![GitHub Release](https://img.shields.io/github/v/release/sumitkolhe/jiosaavn-api)

An Unofficial API for downloading high-quality songs, albums, playlists, and more from [JioSaavn](https://jiosaavn.com).

## 📚 Documentation

Check out the [API documentation](https://saavn.dev/docs) for detailed information on how to use the API.

## 📰 Changelog

For a detailed list of changes, see the [CHANGELOG](CHANGELOG.md).

## 🔌 Running Locally

1. Clone the repository:

   ```sh
   git clone https://github.com/sumitkolhe/jiosaavn-api
   cd jiosaavn-api
   ```

### Using Docker

```sh
docker-compose up
```

OR

### Manually

> [!NOTE]
> You need `Bun(1.0.29+)` or `Node.js(v20+)`

2. Install the required dependencies:

   ```sh
   bun install
   ```

3. Launch the development server:

   ```sh
   bun run dev
   ```

## ☁️ Deploying Your Own Instance

JioSaavn API can be deployed to either Cloudflare Workers or Vercel. Below are the instructions for deploying and finding your deployed API URL.

### Cloudflare Workers

#### Deployment Methods
1. **One-Click Deploy:**
   [![Deploy with Cloudflare Workers](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/sumitkolhe/jiosaavn-api)

2. **Deploy via CLI:**
   ```sh
   bun run deploy
   # or using wrangler directly
   npx wrangler deploy
   ```

#### 📍 How to Find Your Cloudflare Worker URL
After deploying, your API will be hosted on a Cloudflare `.workers.dev` domain (or custom domain if configured).

- **Via Terminal (CLI Output):**
  When you run `bun run deploy` / `npx wrangler deploy`, Wrangler will output your deployed URL at the end of the deployment process:
  ```text
  Published jiosaavn-api (X.XX sec)
    https://jiosaavn-api.<your-subdomain>.workers.dev
  ```

- **Via Cloudflare Dashboard:**
  1. Log in to the [Cloudflare Dashboard](https://dash.cloudflare.com/).
  2. Go to **Workers & Pages** from the left navigation menu.
  3. Click on your worker project (`jiosaavn-api`).
  4. Under **Preview** / **Deployments** or **Routes / Custom Domains**, you will find your primary active URL (e.g., `https://jiosaavn-api.<your-subdomain>.workers.dev`).

---

### Vercel

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/sumitkolhe/jiosaavn-api)

After deployment on Vercel, your URL will be displayed in the Vercel Dashboard under your project overview (e.g., `https://jiosaavn-api.vercel.app`).

---

## 🚀 How to Use the API

Once you have your deployed base URL (e.g. `https://jiosaavn-api.<your-subdomain>.workers.dev`), you can start using all API endpoints by appending `/api` to your base URL.

### 📖 Interactive Documentation
Visit `/docs` or `/swagger` on your deployed URL in your browser to view interactive OpenAPI documentation:
```text
https://<YOUR-DEPLOYED-URL>/docs
```

### 🎵 Usage Examples

Replace `https://<YOUR-DEPLOYED-URL>` with your actual deployed Cloudflare Worker or Vercel URL.

#### 1. Search Endpoints
- **Search Songs:**
  ```http
  GET https://<YOUR-DEPLOYED-URL>/api/search/songs?query=believer
  ```
- **Search Albums:**
  ```http
  GET https://<YOUR-DEPLOYED-URL>/api/search/albums?query=rockstar
  ```
- **Search Artists:**
  ```http
  GET https://<YOUR-DEPLOYED-URL>/api/search/artists?query=arijit
  ```
- **Search Playlists:**
  ```http
  GET https://<YOUR-DEPLOYED-URL>/api/search/playlists?query=weekly+top
  ```

#### 2. Get Details Endpoints
- **Get Song Details (by ID or Link):**
  ```http
  GET https://<YOUR-DEPLOYED-URL>/api/songs?id=S0NG_ID
  GET https://<YOUR-DEPLOYED-URL>/api/songs?link=https://www.jiosaavn.com/song/believer/...
  ```
- **Get Album Details (by ID or Link):**
  ```http
  GET https://<YOUR-DEPLOYED-URL>/api/albums?id=ALBUM_ID
  GET https://<YOUR-DEPLOYED-URL>/api/albums?link=https://www.jiosaavn.com/album/...
  ```
- **Get Artist Details (by ID or Link):**
  ```http
  GET https://<YOUR-DEPLOYED-URL>/api/artists?id=ARTIST_ID
  GET https://<YOUR-DEPLOYED-URL>/api/artists?link=https://www.jiosaavn.com/artist/...
  ```
- **Get Playlist Details (by ID or Link):**
  ```http
  GET https://<YOUR-DEPLOYED-URL>/api/playlists?id=PLAYLIST_ID
  GET https://<YOUR-DEPLOYED-URL>/api/playlists?link=https://www.jiosaavn.com/featured/...
  ```

---

## 📜 License

This project is distributed under the [MIT License](https://opensource.org/licenses/MIT). For more information, see the [LICENSE](LICENSE) file included in this repository.
