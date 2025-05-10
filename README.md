# Deploy project with vercel cli

### Initial Deploy

> [!NOTE]
> You must run lint and build the project before deploy into vercel.
> You should build the project before every re-deploy

**Run following command to check Es-lint error**

```javascript
npm run lint
```

**Run following command to build the project**

```javascript
npm run build
```

**Step 01: Create vercel.json file in the project root directory.**
**step-02: Configure vercel.json file**

```javascript
//For backend
{
  "version": 2,
  "builds": [
    {
      "src": "dist/server.js",
      "use": "@vercel/node"
    }
  ],
  "routes": [
    {
      "src": "/(.*)",
      "dest": "dist/server.js"
    }
  ]
}
//For frontend
{
  "rewrites": [
    {
      "source": "/(.*)",
      "destination": "/"
    }
  ]
}
```

**step-3(optional for first time):If you are first time, must be install version globally by following command:**

```javascript
npm install -g vercel
```

**step-5: Login into vercel by following command(You must login by browser first):**

```javascript
vercel login
```

**step-6: Run following commnad to deploy the project:**

```javascript
vercel --prod
```

**step-6: Click ctrl + mouse to open the inspect. Open an browser link check the building section for show project deploy or not.**
**step-7: Click into the project name of the inspect browser. Go to the project tab and coppy domain link. Lastly, check the link incognito mode.**

### Re-deploy process

**Run following commnad to deploy the project:**

```javascript
vercel --prod
```
