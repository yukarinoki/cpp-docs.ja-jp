---
title: '方法: .NET Framework でのイメージ ファイル形式に変換 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- GDI+ [C++], converting image file formats
- graphics [C++], converting image file formats
ms.assetid: 5d5384b0-b9b7-4262-b9ad-c4cb95f75ee4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 98d55c7ee4ca967a0b52bd87b22e5c316eb1e274
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33130059"
---
# <a name="how-to-convert-image-file-formats-with-the-net-framework"></a>方法: .NET Framework を使用してイメージ ファイル形式を変換する
次のコード例を示しています、<xref:System.Drawing.Image?displayProperty=fullName>クラスおよび<xref:System.Drawing.Imaging.ImageFormat?displayProperty=fullName>列挙型に変換し、イメージ ファイルを保存するために使用します。 次のコードは、.jpg ファイルからイメージを読み込み、.gif、.bmp の両方のファイル形式で保存されます。  
  
## <a name="example"></a>例  
  
```  
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
  
## <a name="see-also"></a>関連項目  
 <xref:System.Drawing>   
 [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)