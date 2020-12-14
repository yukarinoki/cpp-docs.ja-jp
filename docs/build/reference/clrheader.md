---
description: 詳細情報:/clrheader
title: /CLRHEADER
ms.date: 05/16/2019
f1_keywords:
- /CLRHEADER
helpviewer_keywords:
- -CLRHEADER dumpbin option
- /CLRHEADER dumpbin option
- CLRHEADER dumpbin option
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
ms.openlocfilehash: 8866707ae629672c3ae9ebb468d145eafb0475c4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182425"
---
# <a name="clrheader"></a>/CLRHEADER

CLR 固有の情報を表示します。

## <a name="syntax"></a>構文

> /CLRHEADER *file*

### <a name="arguments"></a>引数

*file*<br/>
[/clr](clr-common-language-runtime-compilation.md) でビルドされたイメージ ファイル。

## <a name="remarks"></a>解説

**/CLRHEADER** では、マネージド プログラムで使用されている .NET ヘッダーに関する情報が表示されます。 出力には、.NET ヘッダーの場所、バイト単位のサイズ、ヘッダーのセクションが表示されます。

[/GL](gl-whole-program-optimization.md) コンパイラ オプションで生成したファイルで使用できるのは、[/HEADERS](headers.md) DUMPBIN オプションだけです。

/clr でコンパイルされたファイルで **/CLRHEADER** が使用されているとき、dumpbin 出力に **clr Header:** セクションがあります。 **flags** の値は、使用された /clr オプションを示します。

- 0 -- /clr (イメージにはネイティブ コードが含まれる可能性があります)。

共通言語ランタイムにイメージがビルドされたかどうかをプログラムで確認することもできます。  詳細については、「 [方法: イメージがネイティブであるか CLR であるかを確認する](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md)」を参照してください。

**/clr:pure** および **/clr:safe** コンパイラ オプションは Visual Studio 2015 では非推奨とされており、Visual Studio 2017 以降ではサポートされていません。 "純粋" または "安全" でなければならないコードは C# に移植する必要があります。

## <a name="see-also"></a>関連項目

- [DUMPBIN オプション](dumpbin-options.md)
