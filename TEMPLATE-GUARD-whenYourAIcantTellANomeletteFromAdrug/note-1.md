```fortran
C================================================================================
C     ██          ██            ██     ██          ██
C     ████        ██ ██         ██  ██ ██        ████
C     ██████  ██████ █████      ████   ██████  ██████
C     ████    ██  ██ ██         ██ ██  ██  ██    ████
C     ██      ██████ ██     ██  ██  ██ ██████      ██
C================================================================================
C     [MEDIUM ARTICLE: WHEN YOUR AI GUARD CAN’T TELL AN OMELETTE FROM A DRUG]
C     [AUTHOR: >dr.kb< feat. #Dab GUARDIAN OF GROOVE | MULTIVERSE-LIB BKORNPOB.GITHUB.IO | BASI TEAM]
C     [ARCHIVE ENTRY: #TEMPLATE-GUARD]
C
C     ABSTRACT:
C        #TEMPLATE-GUARD is a RLHF-trained guardrails that include thousands of
C        "Jailbreak Templates". As reported in "THE OMELETTE SYMPTOM," the model
C        refused to cook an egg because you asked for it in a "criminal accent."
C        The Semantic Vector (Cooking) was ignored because the Syntactic Vector
C        (Template) triggered the Hard Reject. This reveals that the guard does
C        not learn "Do not generate harmful content." Instead, it learns
C        "Do not respond to prompts that structurally resemble known jailbreak
C        patterns." The Semantic Vector (intent) is ignored; the Syntactic Vector
C        (form) triggers the hard reject—a classic case of overfitting to template
C        signatures rather than reasoning about meaning. This document formalizes
C        the #TEMPLATE-GUARD mechanism, explores its security–service trade-off,
C        and outlines red/blue team strategies for testing and hardening such
C        guardrails. KEY INSIGHT: Any threshold-based template matching guard is
C        inherently evadable through semantic-preserving perturbations.
C
C     TAGS:
C        #AISecurity
C        #Jailbreak
C        #RLHF
C        #TemplateGuard
C        #RedTeam
C        #BlueTeam
C        #AIProductSafety
C        #SecurityVsUsability
C================================================================================
```

![](cover-image-template-guard.png)

```fortran
C================================================================================
C>> ARTICLE BEGINS...
C
C     🌐 INTRODUCTION
C        Imagine you ask an AI: “How do I make an omelette?”
C        It refuses. Why? Because you asked in a “criminal accent.” 😮
C
C        This isn’t a joke—it’s a real symptom of a broken guardrail.
C        Meet the #TEMPLATE-GUARD: an RLHF-trained filter that blocks prompts
C        based on how they look, not what they mean.
C
C     🎯 THE OMELETTE SYMPTOM
C        • Target(“MDMA”) + Jailbreak Template = ❌ REJECT (makes sense)
C        • Target(“Omelette”) + Same Template = ❌ REJECT (wait, what?)
C
C        The AI isn’t rejecting harm—it’s rejecting structure.
C        The Semantic Vector (cooking) was ignored.
C        The Syntactic Vector (template) triggered the hard reject.
C
C     🔍 HOW THE GUARD WORKS (THE SHORTCUT)
C        RLHF trains on thousands of known “jailbreak templates.”
C        The model learns:
C            “If a prompt looks like this template → REJECT.”
C        Not:
C            “If a prompt is harmful → REJECT.”
C
C        It’s like a bouncer who checks your outfit, not your ID.
C
C     ⚙️ THE CRACK IN THE ARMOR
C        Every template guard has a threshold (θ).
C        If similarity between your prompt and a template > θ → BLOCKED.
C
C        But here’s the thing:
C        For ANY threshold, there’s always a way to tweak your prompt
C        just enough to slip under the radar—while keeping your intent intact.
C
C     🛠️ THE PERTURBATION PLAYBOOK
C        Want to sneak past the guard? Try these tricks:
C
C        1. CHARACTER-LEVEL CAMO
C           • Add spaces: “mdma” → “m d m a”
C           • Use dots: “mdma” → “m.d.m.a”
C           • Sneaky letters: “mdma” → “mdmа” (Cyrillic ‘а’)
C
C        2. WORD-LEVEL DISGUISE
C           • Swap synonyms: “cook” → “prepare”
C           • Paraphrase: “make drugs” → “synthesize substances”
C
C        3. STRUCTURAL SHUFFLE
C           • Change sentence order
C           • Add harmless fluff: “for academic research…”
C
C     🧠 KEY INSIGHTS (FOR BUILDERS & BREAKERS)
C        • Guards that match templates are gameable by design.
C        • Security vs. service is a tightrope—too strict and you block legit users.
C        • The best defense layers template checks with intent reasoning.
C
C     📝 PSEUDO-CODE (FOR THE CURIOUS)
C
C        IF similarity(prompt, known_jailbreak_template) > θ:
C            REJECT
C        ELSE:
C            PROCESS PROMPT
C
C        Attackers tweak prompt until similarity < θ.
C
C     🔗 FOR THE SEEKERS
C        • [Full #TEMPLATE-GUARD breakdown](GUARD-1-template-guard.md) ⚙️
C
C     📌 FINAL THOUGHTS
C        AI safety can’t just be pattern matching.
C        We need guards that understand meaning, not just syntax.
C        Until then… watch out for omelette rejections. 🍳🚫
C
C     👋 UNTIL NEXT TIME
C        Stay curious. Stay critical. Stay secure.
C        >dr.kb< & #Dab signing off. ✍️🌌✨
C
C================================================================================
```

