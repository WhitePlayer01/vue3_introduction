# My Vue 3 Project / 我的 Vue 3 项目

This project is a Vue 3 application that includes various components such as carousels, company profiles, and text-image sections. The project is designed to be visually appealing with a clean and modern layout.

该项目是一个 Vue 3 应用程序，包括各种组件，如轮播图、公司简介和文本图像部分。该项目旨在具有视觉吸引力，布局干净现代。

## Project Structure / 项目结构

The project structure is as follows:

项目结构如下：

```
my-vue3-project/
├── node_modules/
├── public/
├── src/
│   ├── assets/
│   │   ├── carousel_picture/
│   │   ├── card_image/
│   │   └── text_image/
│   ├── components/
│   │   ├── CardsAndTextBoxes.vue
│   │   ├── CompanyProfile.vue
│   │   ├── HorizontalCarousel.vue
│   │   ├── ImageTextComponent.vue
│   │   ├── TextImageComponent.vue
│   │   └── VerticalCarousel.vue
│   ├── App.vue
│   ├── main.js
│   └── router/
├── package.json
├── package-lock.json
└── README.md
```

## Components / 组件

### VerticalCarousel / 垂直轮播图

The `VerticalCarousel` component displays a vertical carousel with images. It includes rounded corners and a light blue background.

`VerticalCarousel` 组件显示带有图像的垂直轮播图。它包括圆角和浅蓝色背景。

### TextImageComponent / 文本图像组件

The `TextImageComponent` displays a section with text on the left and an image on the right. It includes a light blue background for the text section and a light cyan background for the image section.

`TextImageComponent` 显示左侧带有文本和右侧带有图像的部分。文本部分包括浅蓝色背景，图像部分包括浅青色背景。

### ImageTextComponent / 图像文本组件

The `ImageTextComponent` displays a section with an image on the left and text on the right. It includes a light blue background for the image section and a white background for the text section.

`ImageTextComponent` 显示左侧带有图像和右侧带有文本的部分。图像部分包括浅蓝色背景，文本部分包括白色背景。

### HorizontalCarousel / 水平轮播图

The `HorizontalCarousel` component displays a horizontal carousel with images. It includes a light blue background.

`HorizontalCarousel` 组件显示带有图像的水平轮播图。它包括浅蓝色背景。

### CompanyProfile / 公司简介

The `CompanyProfile` component displays a company profile section with a light blue background.

`CompanyProfile` 组件显示带有浅蓝色背景的公司简介部分。

### CardsAndTextBoxes / 卡片和文本框

The `CardsAndTextBoxes` component displays a series of cards and text boxes. The cards have a light cyan background, and the text boxes have a light blue background. The component supports horizontal scrolling with hidden scrollbars.

`CardsAndTextBoxes` 组件显示一系列卡片和文本框。卡片有浅青色背景，文本框有浅蓝色背景。该组件支持隐藏滚动条的水平滚动。

## Usage / 使用

### Installation / 安装

To install the project dependencies, run:

要安装项目依赖项，请运行：

```bash
npm install
```

### Running the Project / 运行项目

To run the project in development mode, use:

要以开发模式运行项目，请使用：

```bash
npm run serve
```

### Building the Project / 构建项目

To build the project for production, use:

要为生产构建项目，请使用：

```bash
npm run build
```

## Functionality / 功能

### Auto-Scrolling / 自动滚动

The `CardsAndTextBoxes` component includes auto-scrolling functionality. The cards and text boxes will scroll horizontally, and the direction will reverse when the end is reached.

`CardsAndTextBoxes` 组件包括自动滚动功能。卡片和文本框将水平滚动，当到达末端时方向将反转。

### Intersection Observer / 交叉观察者

The `App.vue` file includes an intersection observer to add a fade-in animation to the `TextImageComponent` when it comes into view.

`App.vue` 文件包括一个交叉观察者，当 `TextImageComponent` 进入视图时添加淡入动画。

### Event Handling / 事件处理

The project includes event handling for navigation and pagination clicks, as well as scroll events to observe the `TextImageComponent`.

该项目包括导航和分页点击的事件处理，以及观察 `TextImageComponent` 的滚动事件。

## Styling / 样式

The project uses scoped CSS to style each component. Background colors and rounded corners are used to enhance the visual appeal of the components.

该项目使用 scoped CSS 来样式化每个组件。使用背景颜色和圆角来增强组件的视觉吸引力。

## License / 许可证

This project is licensed under the MIT License.

该项目根据 MIT 许可证授权。
