<script lang="ts">
    import { onMount } from "svelte";
    import { browser } from "$app/environment";
    import gsap from "gsap";
    import ScrollTrigger from "gsap/dist/ScrollTrigger";

    import Footer from "$lib/components/Footer.svelte";
    import Scene from "$lib/components/Scene.svelte";



    if (browser) {
        gsap.registerPlugin(ScrollTrigger);
    }

    onMount(() => {
        // Scroll Indicator
        gsap.to("#mouse", {
            opacity: 0,
            scrollTrigger: {
                trigger: "#content",
                start: "top bottom-=100",
                end: "top bottom-=100",
                scrub: true,
                // markers: true,
            },
        });
    });

    interface TeamMember {
        name: string;
        image: string;
        devPostLink: string;
        githubLink: string;
    }

</script>

<div class="relative">
    <div class="relative">
        <section
            class="grid min-h-screen h-full pb-40 pt-12 grid-cols-5 max-w-screen-xl mx-auto"
        >
            <div class="pt-20 col-span-3">
                <h1
                    class="mb-4 text-4xl font-mono tracking-tighter !leading-[1.2] font-bold md:text-5xl xl:text-6xl"
                >
                    Hands-On Learning with
                    <span
                        class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary"
                    >
                        Virtual Credentials
                    </span>
                </h1>
                <p class="mb-6 text-slate-500 md:mb-10 md:text-lg lg:text-xl">
                    Connecting Medical Knowledge with Real-World Application.
                </p>
                <div>
                    <a
                        class="bg-primary hover:bg-primary-dark transition-colors text-white rounded-lg px-6 py-4"
                        href="/simulation"
                    >
                        Begin Simulation
                    </a>
                </div>
            </div>
            <div class="col-span-2">
                <Scene />
            </div>
        </section>
    </div>

    <div
        class="w-10 h-16 border-[3px] border-slate-400 rounded-3xl fixed z-20 bottom-8 left-1/2 before:w-3 before:h-3 before:absolute before:top-2 before:left-1/2 before:-translate-x-1/2 before:bg-slate-400 before:rounded-full before:animate-wheel transition-opacity"
        id="mouse"
    />

<div class="flex flex-col pt-12" id="content">
    <div class="max-w-screen-lg mx-auto">
        <section>
            <h2 class="text-6xl font-bold text-center mb-16">About SimCare</h2>
            <p class="mb-4 text-lg text-slate-600">
                SimCare allows for an interactive learning environment to fill a training gap specifically in clinical decision-making in healthcare. Unlike conventional micro-credentialing methods, SimCare evaluates clinical diagnosis with a user interface that more closely resembles real-life conditions so that users can make quick, data-driven decisions based both on time and accuracy.
            </p>
            <p class="mb-4 text-lg text-slate-600">
                This platform offers users a practical, immersive way to cope with clinical challenges. Tackling these challenges requires them to process n amounts of qualitative and quantitative data within time constraints. By conducting simulations in real-time, SimCare serves as a conduit from education to real-time employment demands by the healthcare industry.
            </p>
            <p class="mb-4 text-lg text-slate-600">
                Experience our interactive simulations designed to hone clinical decision-making skills, providing a more accessible and affordable solution compared to traditional training methods.

            </p>
            <section class="mt-12">
                <h3 class="text-4xl font-semibold mb-8">How SimCare Works</h3>
                <p class="mb-4 text-lg text-slate-600">
                    SimCare was developed using SvelteKit, a performance-driven framework for building web applications, paired with TypeScript for enhanced data typing and development efficiency. The platform’s styling is powered by TailwindCSS, enabling rapid design iteration with minimal CSS. Additionally, libraries like Three.js, GSAP, and Melt UI were integrated to provide a smooth, interactive user experience.
                </p>
            </section>
            <section class="mt-12">
                <h3 class="text-4xl font-semibold mb-8">Challenges and Achievements</h3>
                <p class="mb-4 text-lg text-slate-600">
                    Building SimCare was not without its challenges. Crafting a design that effectively mirrored real-life clinical scenarios took significant time, as did deciding on the structure of the simulation (turn-based vs. continuous timeline). We also faced the painstaking task of compiling accurate data for medications, health indicators, and diseases to ensure the simulations were both realistic and effective.
                </p>
                <p class="mb-4 text-lg text-slate-600">
                    Despite these hurdles, we are extremely proud of the final product, created within a tight timeline using a blend of innovative tools, APIs, and, of course, teamwork. Our team collaborated efficiently using tools like GitHub and VSCode Liveshare, ensuring smooth development cycles.
                </p>
            </section>
            <section class="mt-12">
                <h3 class="text-4xl font-semibold mb-8">What’s Next for SimCare</h3>
                <p class="mb-4 text-lg text-slate-600">
                    Looking forward, SimCare aims to expand its capabilities by adding more treatments, medical conditions, and advanced simulation components. We are working towards collaborating with healthcare professionals to enhance the platform’s accuracy and eventually provide accredited certifications upon successful completion.
                </p>
            </section>
            <div class="flex justify-center mt-8">
                <!-- Additional content or links to explore more -->
            </div>
        </section>
    </div>
</div>



    <Footer />
</div>
