# After_Refresh_Refresh_page_Refresh_effect
### 1.Add on Global/index.css
```jsx
/*==================================== Landing page refresh intro ============================*/
.landing-intro {   /* Used in navabr bottom to top */
    opacity: 0;
    transform: translateY(0px);
    transition: opacity 0.8s ease-out, transform 0.8s ease-out;
    will-change: opacity, transform;
}

.landing-intro-loaded {
    opacity: 1;
    transform: translateY(0);
}

.hero-intro {
    opacity: 0;
    transform: translateY(40px) scale(0.99);
    transition: opacity 1s ease-out 0.15s, transform 1s ease-out 0.15s;
    will-change: opacity, transform;
}

.hero-intro-loaded {
    opacity: 1;
    transform: translateY(0) scale(1);
}

@media (prefers-reduced-motion: reduce) {

    .landing-intro,
    .hero-intro {
        opacity: 1;
        transform: none;
        transition: none;
    }
}
```
### 2. Place css and useEffect on Main Page/ Layout/ Root page

```jsx
const LandingPage = () => {
    const [isLoaded, setIsLoaded] = useState(false)

    useEffect(() => {
        // Reset scroll position on refresh, then trigger intro animation.
        window.scrollTo({ top: 0, left: 0, behavior: 'auto' })
        const timer = setTimeout(() => setIsLoaded(true), 70)

        return () => clearTimeout(timer)
    }, [])


    return (
        <div className={`landing-intro ${isLoaded ? 'landing-intro-loaded' : ''}`}>
            <nav>
                <Navbar />
            </nav>
            <section
                id="home"
                className={`hero-intro ${isLoaded ? 'hero-intro-loaded' : ''}`}
            >
                <HeroPage />
            </section>
            <section id="how-it-work">
                <HowItWork />
            </section>

            <section id="feature">
                <PowerfullFeature />
            </section>

            <section id="transparency">
                <Transparency />
            </section>
            <section id="privacy-security">
                <PrivacyAndSecurity />
            </section>
            <section id="about">
                <AboutPage />
            </section>
            <section id="contact">
                <ContactPaage />
            </section>
            <section id="get-started">
                <PlaystoreDownloadPage />
            </section>

            <section>
                <Footer />
            </section>
        </div>
    )
}

```



## My Guitar Repos – Quick Links

All my feature docs live in separate repos. Click any to jump straight to its README.

| Repo Name              | Description                          | Link                                      |
|------------------------|--------------------------------------|-------------------------------------------|
| custom-folks-ad        | Custom ads for folks platform        |[](https://github.com/yourusername/custom-folks-ad#readme) |
| guitar-hero-ui         | Hero section animations + scroll     |[](https://github.com/yourusername/guitar-hero-ui#readme) |
| smooth-nav-scroll      | Single-page smooth redirect system   |[](https://github.com/yourusername/smooth-nav-scroll#readme) |
| privacy-policy-gen     | Auto-gen privacy & security pages    |[](https://github.com/yourusername/privacy-policy-gen#readme) |
| guitar-analytics       | Real-time usage tracking             |[](https://github.com/yourusername/guitar-analytics#readme) |
| auth-flow-v2           | Auth + social login boilerplate      |[](https://github.com/yourusername/auth-flow-v2#readme) |
| guitar-footer-kit      | Reusable footer with socials         |[](https://github.com/yourusername/guitar-footer-kit#readme) |

**Tip:** Replace `yourusername` with your actual GitHub username.  
If you ever add more—just copy-paste a row. Keeps everything one glance away.



















