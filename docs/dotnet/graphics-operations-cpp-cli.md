---
description: 詳細については、「グラフィックス操作 (C++/CLI)」を参照してください。
title: グラフィック操作 (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- GDI+ [C++]
- .NET Framework [C++], graphics
- images [C++], .NET Framework and
- GDI+ [C++], about graphics operations
- graphics [C++], .NET Framework and
- GDI+ [C++], displaying images
- graphics [C++], displaying images
- GDI+, drawing shapes
- drawing, shapes
- shapes
- shapes, drawing
- GDI+ [C++], rotating images
- graphics [C++], rotating images
- GDI+ [C++], converting image file formats
- graphics [C++], converting image file formats
ms.assetid: bba27228-b9b3-4c9c-b31c-a04b76702a95
ms.openlocfilehash: 84dbc75aa306219b8733848ece5c594ca40a0489
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223543"
---
# <a name="graphics-operations-ccli"></a>グラフィック操作 (C++/CLI)

Windows SDK を使用したイメージ操作を示します。

次のトピックでは、<xref:System.Drawing.Image?displayProperty=fullName> クラスを使用してイメージ操作を実行する方法を説明します。

## <a name="display-images-with-the-net-framework"></a><a name="display"></a> .NET Framework を使用したイメージの表示

次のコード例では、OnPaint イベントハンドラーを変更して、メインフォームのオブジェクトへのポインターを取得し <xref:System.Drawing.Graphics> ます。 <xref:System.Windows.Forms.Form.OnPaint%2A>関数は、Visual Studio アプリケーションウィザードを使用して作成される可能性のある Windows フォームアプリケーションを対象としています。

イメージはクラスによって表され <xref:System.Drawing.Image> ます。 画像データは、メソッドを使用して .jpg ファイルから読み込まれます <xref:System.Drawing.Image.FromFile%2A?displayProperty=fullName> 。 画像がフォームに描画される前に、画像に合わせてフォームのサイズが変更されます。 イメージの描画は、メソッドを使用して実行され <xref:System.Drawing.Graphics.DrawImage%2A?displayProperty=fullName> ます。

<xref:System.Drawing.Graphics>クラスと <xref:System.Drawing.Image> クラスは両方とも <xref:System.Drawing?displayProperty=fullName> 名前空間にあります。

### <a name="example"></a>例

```cpp
#using <system.drawing.dll>

using namespace System;
using namespace System::Drawing;

protected:
virtual Void Form1::OnPaint(PaintEventArgs^ pe) override
{
    Graphics^ g = pe->Graphics;
    Image^ image = Image::FromFile("SampleImage.jpg");
    Form::ClientSize = image->Size;
    g->DrawImage( image, 0, 0, image->Size.Width, image->Size.Height );
}
```

## <a name="draw-shapes-with-the-net-framework"></a><a name="draw"></a> .NET Framework を使用した図形の描画

次のコード例では、クラスを使用して、 <xref:System.Drawing.Graphics> <xref:System.Windows.Forms.Form.OnPaint%2A> メインフォームのオブジェクトへのポインターを取得するようにイベントハンドラーを変更し <xref:System.Drawing.Graphics> ます。 このポインターを使用して、フォームの背景色を設定し、メソッドとメソッドを使用して直線と円弧を描画し <xref:System.Drawing.Graphics.DrawLine%2A?displayProperty=fullName> <xref:System.Drawing.Graphics.DrawArc%2A> ます。

### <a name="example"></a>例

```cpp
#using <system.drawing.dll>
using namespace System;
using namespace System::Drawing;
// ...
protected:
virtual Void Form1::OnPaint(PaintEventArgs^ pe ) override
{
   Graphics^ g = pe->Graphics;
   g->Clear(Color::AntiqueWhite);

   Rectangle rect = Form::ClientRectangle;
   Rectangle smallRect;
   smallRect.X = rect.X + rect.Width / 4;
   smallRect.Y = rect.Y + rect.Height / 4;
   smallRect.Width = rect.Width / 2;
   smallRect.Height = rect.Height / 2;

   Pen^ redPen = gcnew Pen(Color::Red);
   redPen->Width = 4;
   g->DrawLine(redPen, 0, 0, rect.Width, rect.Height);

   Pen^ bluePen = gcnew Pen(Color::Blue);
   bluePen->Width = 10;
   g->DrawArc( bluePen, smallRect, 90, 270 );
}
```

## <a name="rotate-images-with-the-net-framework"></a><a name="rotate"></a> .NET Framework を使用してイメージを回転させる

次のコード例は、クラスを使用して <xref:System.Drawing.Image?displayProperty=fullName> ディスクからイメージを読み込み、90°回転して、新しい .jpg ファイルとして保存する方法を示しています。

### <a name="example"></a>例

```cpp
#using <system.drawing.dll>

using namespace System;
using namespace System::Drawing;

int main()
{
   Image^ image = Image::FromFile("SampleImage.jpg");
   image->RotateFlip( RotateFlipType::Rotate90FlipNone );
   image->Save("SampleImage_rotated.jpg");
   return 0;
}
```

## <a name="convert-image-file-formats-with-the-net-framework"></a><a name="convert"></a> イメージファイル形式を .NET Framework に変換します

次のコード例は、 <xref:System.Drawing.Image?displayProperty=fullName> <xref:System.Drawing.Imaging.ImageFormat?displayProperty=fullName> イメージファイルの変換と保存に使用されるクラスと列挙を示しています。 このコードでは、イメージを .jpg ファイルから読み込み、.gif ファイル形式と .bmp ファイル形式の両方で保存します。

### <a name="example"></a>例

```cpp
#using <system.drawing.dll>

using namespace System;
using namespace System::Drawing;
using namespace System::Drawing::Imaging;

int main()
{
   Image^ image = Image::FromFile("SampleImage.jpg");
   image->Save("SampleImage.png", ImageFormat::Png);
   image->Save("SampleImage.bmp", ImageFormat::Bmp);

   return 0;
}
```

## <a name="related-sections"></a>関連項目

[グラフィックス プログラミングについて](/dotnet/framework/winforms/advanced/getting-started-with-graphics-programming)

[GDI+ マネージド コードについて](/dotnet/framework/winforms/advanced/about-gdi-managed-code)

## <a name="see-also"></a>関連項目

[C++/CLI を使用した .NET プログラミング (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

<xref:System.Drawing>
