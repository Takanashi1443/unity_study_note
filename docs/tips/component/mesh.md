## Tips - 注意が必要なコンポーネント - Mesh FilterとMesh Renderer

-[Tipsへ](./../../)

### Mesh FilterとMesh Renderer

Mesh自体には、各メッシュにn番目のマテリアルが割り当てられているといった情報や、各頂点のUV座標情報が保持されている。

Mesh Filterは、GameObjectがどのMeshを参照するかを示す、言わばMeshの入れ物である。

一方で、Meshにはどのマテリアルを参照するかという情報は含まれておらず、それはMesh Rendererで指定するようになっている。

従って、Mesh Filterで同じMeshを参照しているコンポーネントでも、Mesh Rendererに異なるマテリアルを割り当てれば見た目が異なるGameObjectになる。


