---
title: /CLRHEADER
ms.date: 11/04/2016
f1_keywords:
- /CLRHEADER
helpviewer_keywords:
- -CLRHEADER dumpbin option
- /CLRHEADER dumpbin option
- CLRHEADER dumpbin option
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
ms.openlocfilehash: 6a1240e2d3ad2ac3a454c610a6f49d07e50951e5
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820703"
---
# <a name="clrheader"></a>/CLRHEADER

CLR に固有の情報を表示します。

## <a name="syntax"></a>構文

> /CLRHEADER *file*

### <a name="arguments"></a>引数

*file*<br/>
ビルドされたイメージ ファイル[/clr](clr-common-language-runtime-compilation.md)します。

## <a name="remarks"></a>Remarks

**/CLRHEADER**マネージ プログラムで使用される .NET ヘッダーに関する情報が表示されます。 出力は、ヘッダーのセクションでは、.NET のヘッダーのバイト単位での位置やサイズを示します。

のみ、 [/HEADERS](headers.md) DUMPBIN オプションがで生成されたファイルで使用できる、 [/GL](gl-whole-program-optimization.md)コンパイラ オプション。

ときに **/CLRHEADER**使用は/clr でコンパイルされたファイルがあります、 **clr ヘッダー:** dumpbin 出力セクション。 値**フラグ**/clr オプションが使用されたことを示します。

- 0 -/clr (イメージは、ネイティブ コードを含めることができます)。

共通言語ランタイムのイメージをビルドしたかどうかもプログラムで確認できます。  詳細については、「[方法 :イメージがネイティブ モードまたは CLR であるか判断](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md)します。

**/Clr: 純粋な**と **/clr:safe**コンパイラ オプションは Visual Studio 2015 で非推奨とされ、Visual Studio 2017 でサポートされていません。 「純粋」または「安全」にする必要があるコードを移植する必要があるC#します。

## <a name="see-also"></a>関連項目

- [DUMPBIN オプション](dumpbin-options.md)
