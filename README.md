# 🚀 React TypeScript UI 模板 | React TypeScript UI Template

一个精心设计的现代化React + TypeScript + Tailwind CSS模板，内置完整的UI组件库和设计系统。

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![TypeScript](https://img.shields.io/badge/TypeScript-5.5-blue)
![React](https://img.shields.io/badge/React-18.3-61dafb)
![Tailwind](https://img.shields.io/badge/Tailwind-3.4-38bdf8)

## ✨ 核心特性

- 🎨 **现代设计系统** - 基于设计令牌的完整主题配置
- 🌙 **明暗主题支持** - 预配置的CSS变量主题系统
- 🔧 **TypeScript** - 完整的类型安全保障
- 📱 **响应式设计** - 移动优先的响应式组件
- ⚡ **高性能** - 基于Vite的极速开发体验
- 🎯 **无障碍性** - 遵循WCAG标准的可访问性设计

## 🛠️ 技术栈

- **React 18** + **TypeScript 5.5**
- **Vite 5.4** - 构建工具
- **Tailwind CSS 3.4** - 样式框架
- **Radix UI** - 无障碍组件基础
- **Lucide React** - 图标库

## 🚀 快速开始

### 1. 克隆模板

```bash
# 克隆项目
git clone <your-repo-url>
cd bolt-vite-react-ts-template

# 安装依赖
npm install
```

### 2. 启动开发

```bash
# 开发模式
npm run dev

# 构建生产版本
npm run build

# 预览构建结果
npm run preview
```

## 📦 内置组件库

### 基础组件
- **Button** - 多变体按钮 (default, outline, ghost, destructive)
- **Card** - 卡片容器和内容组件
- **Input** - 输入框组件
- **Label** - 表单标签
- **Badge** - 状态徽章
- **Avatar** - 用户头像

### 表单组件
- **Checkbox** - 复选框
- **RadioGroup** - 单选框组
- **Select** - 下拉选择器
- **Slider** - 滑块组件
- **Switch** - 开关切换
- **Textarea** - 多行文本输入

### 布局组件
- **Tabs** - 标签页切换
- **Accordion** - 折叠面板
- **Dialog** - 模态对话框
- **Popover** - 弹出层
- **Separator** - 分隔线
- **Progress** - 进度条

### 导航组件
- **Dropdown Menu** - 下拉菜单
- **Hover Card** - 悬浮卡片
- **Tooltip** - 工具提示
- **Toggle** - 切换按钮

## 🎨 主题系统

### CSS变量配置

参考 src/styles/theme.css 中定义的CSS变量。

### 主题切换实现

可以通过添加/移除 `dark` 类来切换主题：

```tsx
// 切换到暗色主题
document.documentElement.classList.add('dark')

// 切换到亮色主题
document.documentElement.classList.remove('dark')

// 检测系统主题偏好
const prefersDark = window.matchMedia('(prefers-color-scheme: dark)').matches
```

## 🔧 组件使用示例

### 按钮组件

```tsx
import { Button } from './components/ui/button'

<Button>默认按钮</Button>
<Button variant="outline">轮廓按钮</Button>
<Button variant="ghost">幽灵按钮</Button>
<Button size="lg">大按钮</Button>
```

### 表单组件

```tsx
import { Input } from './components/ui/input'
import { Label } from './components/ui/label'
import { Select, SelectContent, SelectItem, SelectTrigger, SelectValue } from './components/ui/select'

<div className="space-y-4">
  <div className="space-y-2">
    <Label htmlFor="email">邮箱</Label>
    <Input id="email" type="email" placeholder="输入邮箱" />
  </div>
  
  <div className="space-y-2">
    <Label>选择选项</Label>
    <Select>
      <SelectTrigger>
        <SelectValue placeholder="请选择" />
      </SelectTrigger>
      <SelectContent>
        <SelectItem value="option1">选项1</SelectItem>
        <SelectItem value="option2">选项2</SelectItem>
      </SelectContent>
    </Select>
  </div>
</div>
```

### 卡片组件

```tsx
import { Card, CardContent, CardDescription, CardHeader, CardTitle } from './components/ui/card'

<Card>
  <CardHeader>
    <CardTitle>卡片标题</CardTitle>
    <CardDescription>卡片描述信息</CardDescription>
  </CardHeader>
  <CardContent>
    <p>卡片内容...</p>
  </CardContent>
</Card>
```

## 📱 响应式设计

Tailwind CSS响应式断点：

```tsx
<div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
  {/* 移动端1列，平板2列，桌面3列 */}
</div>
```

- `sm`: 640px+
- `md`: 768px+  
- `lg`: 1024px+
- `xl`: 1280px+
- `2xl`: 1536px+

## 🛡️ TypeScript 配置

项目使用严格的TypeScript配置，确保类型安全：

```json
{
  "compilerOptions": {
    "strict": true,
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "exactOptionalPropertyTypes": true
  }
}
```

## 📁 项目结构

```
src/
├── components/
│   ├── ui/           # UI组件库
│   │   ├── button.tsx
│   │   ├── card.tsx
│   │   ├── input.tsx
│   │   └── ...
│   ├── theme-provider.tsx
│   └── theme-toggle.tsx
├── styles/
│   └── globals.css   # 全局样式和主题变量
├── App.tsx
└── main.tsx
```

## 🔨 自定义开发

### 添加新组件

1. 在 `src/components/ui/` 创建组件文件
2. 使用 `class-variance-authority` 定义变体
3. 遵循现有的设计模式

```tsx
import { cva, type VariantProps } from "class-variance-authority"
import { cn } from "./utils"

const componentVariants = cva(
  "base-classes",
  {
    variants: {
      variant: {
        default: "default-classes",
        secondary: "secondary-classes",
      },
    },
    defaultVariants: {
      variant: "default",
    },
  }
)

export interface ComponentProps
  extends React.HTMLAttributes<HTMLDivElement>,
    VariantProps<typeof componentVariants> {}

export function Component({ className, variant, ...props }: ComponentProps) {
  return (
    <div 
      className={cn(componentVariants({ variant, className }))} 
      {...props} 
    />
  )
}
```

### 扩展主题

在 `tailwind.config.js` 中添加自定义配置：

```javascript
export default {
  theme: {
    extend: {
      colors: {
        brand: {
          50: '#f0f9ff',
          500: '#3b82f6',
          900: '#1e3a8a',
        }
      }
    },
  },
}
```

## 📄 许可证

MIT License - 可自由使用、修改和分发。

## 🤝 贡献

欢迎提交Issue和Pull Request来改进这个模板！

---

**开始您的现代化React应用开发之旅 🚀**