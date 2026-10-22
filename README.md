# SURF🏄: Surprise-driven Uncertainty Re-inflation and Fine tuning

The offcial, complete codebase of SURF, a submission for AAMAS 2027.

This codebase reproduces the main, component ablation, and planner ablation for all experiments used in paper. Note that this codebase is not the version submitted to AAMAS - latter only includes all `Pendulum-v1` experiments.

Openreview link can be found [here](https://openreview.net/forum?id=zDMepiMxdI&referrer=%5Bthe%20profile%20of%20Yuanhe%20Li%5D(%2Fprofile%3Fid%3D~Yuanhe_Li1)).

```bash
pip install mbrl==0.1.5 --no-deps && pip install -r requirements.txt
```

Run from the repo root. Results go to `results/`.

**FrozenLake** (`--change-p` = post-change p′: 0.9 / 0.7 / 0.5 / 0.3 / 0.1)
```bash
python FrozenLake/sweep_unfrozen_layers.py --n-unfrozen 1 --trials 99 \
    --cvar-alpha 0 --clip-delta-n 2 --change-p 0.7 --out-dir results/fl_clip2_n99
python FrozenLake/summarize_clip2_n99.py
```

**NS-Bridge**
```bash
(cd Bridge && bash run_bridge_ablation.sh)
python Bridge/summarize_bridge_ablation.py
```

**Pendulum**
```bash
(cd pendulum-reproduce && python run_main.py)
```

**Reacher**: see `Reacher/README.md`.
