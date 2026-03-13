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
