<style>
    /* Keyframe for the slow, breathing glow */
    @keyframes subtle-glow {
        0% { background-position: 10% 10%, 90% 90%, center; }
        50% { background-position: 12% 8%, 88% 92%, center; }
        100% { background-position: 10% 10%, 90% 90%, center; }
    }

    body {
        font-family: Inter, system-ui, sans-serif;
        transition: background 0.6s ease, color 0.4s ease;
    }

    /* ---- LIGHT MODE ---- */
    body {
        background: linear-gradient(180deg, #fffaf3 0%, #fff5e1 100%);
        color-scheme: light;
    }

    /* ---- DARK MODE (with Animation) ---- */
    .dark body {
        /* Enhanced background definitions for the animation */
        background: radial-gradient(800px at 10% 10%, rgba(99,102,241,0.2), transparent 40%),
                    radial-gradient(900px at 90% 90%, rgba(139,92,246,0.18), transparent 50%),
                    linear-gradient(180deg,#0a0f1d 0%, #111827 80%);
        color-scheme: dark;
        /* Apply the animation */
        animation: subtle-glow 20s ease-in-out infinite alternate;
        background-size: 100% 100%, 100% 100%, 100% 100%; /* Ensures backgrounds are sized correctly for position changes */
    }

    /* Glass cards */
    .card {
        backdrop-filter: blur(8px) saturate(1.05);
        -webkit-backdrop-filter: blur(8px);
        transition: background 0.4s ease, border 0.4s ease, box-shadow 220ms;
    }

    /* Light Mode Card (Default) */
    body .card {
        background: rgba(255,255,255,0.8);
        border: 1px solid rgba(16,24,40,0.05);
    }

    /* Dark Mode Card */
    .dark body .card {
        background: rgba(17,24,39,0.55);
        border: 1px solid rgba(255,255,255,0.05);
    }

    /* Tilt effect */
    .tilt {
        transform-style: preserve-3d;
        transition: transform 220ms cubic-bezier(.2,.9,.3,1), box-shadow 220ms;
        will-change: transform;
    }
    .tilt:hover { box-shadow: 0 12px 40px rgba(2,6,23,0.18), 0 0 0 1px rgba(2,6,23,0.05); }
    .dark .tilt:hover { box-shadow: 0 12px 40px rgba(0,0,0,0.4), 0 0 0 1px rgba(255,255,255,0.08); }


    /* skill tag hover */
    .skill {
        transition: transform .22s ease, box-shadow .22s ease;
    }
    .skill:hover { transform: translateY(-4px) scale(1.03); box-shadow: 0 8px 30px rgba(2,6,23,0.08); }

    /* reveal */
    .reveal { opacity: 0; transform: translateY(18px); transition: all 600ms cubic-bezier(.2,.9,.3,1); }
    .reveal.visible { opacity: 1; transform: translateY(0); }

    /* warm accent for buttons in light, neon glow in dark */
    .accent {
        background: linear-gradient(90deg, #fb923c, #f59e0b);
        color: white;
        box-shadow: 0 6px 20px rgba(245,158,11,0.15);
    }
    .dark .accent {
        background: linear-gradient(90deg,#7c3aed,#06b6d4);
        box-shadow: 0 10px 40px rgba(99,102,241,0.12), 0 2px 8px rgba(6,182,212,0.06);
    }

    /* small helpers */
    .muted { color: rgba(2,6,23,0.6); }
    .dark .muted { color: rgba(255,255,255,0.65); }
    .focus-ring:focus { outline: none; box-shadow: 0 0 0 4px rgba(99,102,241,0.12); border-radius: 12px; }

    html { scroll-behavior: smooth; }
</style>
