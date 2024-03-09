# Tiny 3DGStreamViewer
This is a fork of [GaussianSplattingViewer](https://github.com/limacv/GaussianSplattingViewer), as a simple viewer for our CVPR 2024 paper [3DGStream](https://sjojok.github.io/3dgstream/).

Note this is not the renderer we used to evaluate the render performance of 3DGStream in our paper "3DGStream: On-the-Fly Training of 3D Gaussians for Efficient Streaming of Photo-Realistic Free-Viewpoint Videos", but is still efficient enough for real-time renderable FVVs

## Availble FVVs:

[Flame Steak](https://drive.google.com/file/d/1AXDqSzSaT_uNu_DhKeSmZmrBAfuOhWYY/view?usp=drive_link)


## Installation
The repository contains submodules, check it out with --recursive
```shell
git clone https://github.com/henrypearce4D/3DGStreamViewer.git --recursive
```

Create anaconda environment and install the dependencies:
```
cd 3DGStreamViewer
conda env create --file environment.yml
conda activate 3dgstream_viewer
```

Build tiny-cuda-nn
```
cd submodules\tiny-cuda-nn
cmake . -B build -DCMAKE_BUILD_TYPE=RelWithDebInfo
cmake --build build --config RelWithDebInfo -j
```

## Usage
Launch the viewer:
```
python main.py
```

### To view Free-Viewpoint Videos of 3DGStream

1. Unzip the zip file at anywhere you like

   ![image](https://github.com/SJoJoK/3DGStreamViewer/assets/50450335/011675a5-d8d6-410e-ab82-5572e71fe6bd)

2. Launch the viewer:
   
    ```
    python main.py
    ```

3. Click `load ply` and open the `init_3dgs.ply`

   ![image](https://github.com/SJoJoK/3DGStreamViewer/assets/50450335/c5879abe-7752-4229-ae09-d71992ab3114)

4. Move the camera to a proper position

   ![image](https://github.com/SJoJoK/3DGStreamViewer/assets/50450335/3e4c437a-ba1e-40f8-b022-3e88090b2a97)

5. Click `load FVV` and choose the directory where you unzip the FVV

6. Click `Step` to step into next frame, click `Play` or `Pause` to play or pause the FVV, and click `Reset` to get back to Frame 0

Happy Hacking!

## TO-DO List (Not guaranteed)

- [ ] View the results of Stage 1 and/or Stage 2
- [ ] Support OpenGL-backend
- [ ] Align the functionality with the origin repo.

## Code-paper discrepancies

1. We discarded the SH rotation, as stated in the paper, due to its costly and unnecessary.
2. The renderer we used to evaluate the render performance is the official [SIBR Viewer](https://gitlab.inria.fr/sibr/sibr_core), which has an highly-optimized OpenGL backend. While, we believe that an open-srouce viewer based on CUDARasterizer is more configurable and helpful for researchers.

## Contributing

This project is a tiny viewer designed for simplicity and ease of use. We welcome contributions that aim to improve performance or extend functionality. If you have ideas or improvements, please feel free to submit a pull request.

## Acknowledgements

We would like to express our gratitude to the original repository [GaussianSplattingViewer](https://github.com/limacv/GaussianSplattingViewer) for providing the foundation upon which this work is built.

