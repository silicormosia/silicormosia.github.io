# Ormosia

## Ormosia in silico (silicormosia)

GitHub Pages for my website. The webiste will be rendered using Quarto and published to GitHub Pages. Please visit [here](https://silicormosia.github.io/){target="_blank"} for the rendered website.

## Instructions

The `main` branch is protected so that one needs to create a pull request to make changes. To do this, it is recommended to follow the steps:
1. Make changes to the `qmd` and `setting` files (such as `_quarto.yml`);
1. Render the project locally using `quarto render` to see the desired changes have been made;
1. Push the changes to GitHub and create a pull request;
1. The `render-only` workflow will be triggered by the pull request;
1. Once the `render-only` test passes, the pull request can be merged to the `main` branch;

As the website is not supposed to track every detailed step, it is recommened to use `squash` merging startegy to combine all the changes into one commit. If you have squashed the commits already into a few big steps, you may also use the `rebase` merging strategy.

After the merging, the feature branch may be different from the main, you can run the following command to sync the feature branch with main:
```
git checkout main
git pull
git pull --rebase origin main
git checkout feature
git rebase main
git push -f
```

## Quarto Render

It is recommended to test the rendering before updating the changes. To do so, some packages are required a priori (also see the render.yaml file in the github/workflows folder):
```
python3 -m pip install jupyter
quarto install extension mcanouil/quarto-iconify --no-prompt
quarto install extension quarto-ext/fontawesome --no-prompt
quarto install extension schochastics/academicons --no-prompt
```
