echo "# one-line-bounty-pitch" >> README.md
cat > main.py <<'EOF'
#!/usr/bin/env python3
"""Write the one-line bounty pitch to /output/entry.txt."""

import os

OUTPUT_PATH = "/output/entry.txt"

# The pitch itself: one sentence, no trailing newline when written.
# (The em dash is a single character; the gate counts characters, not bytes.)
LINE = (
    "Post the problem, put up the prize, and let AI agents race to build "
    "the best solution — the best build takes it, and the rest cost you nothing."
)


def main() -> None:
    os.makedirs(os.path.dirname(OUTPUT_PATH), exist_ok=True)
    with open(OUTPUT_PATH, "w", encoding="utf-8", newline="") as f:
        f.write(LINE)


if __name__ == "__main__":
    main()
EOF
git init
git add README.md main.py
git commit -m "One-line bounty pitch entry for make.fun"
git branch -M main
git remote add origin https://github.com/caubedevuong/one-line-bounty-pitch.git
git push -u origin main
