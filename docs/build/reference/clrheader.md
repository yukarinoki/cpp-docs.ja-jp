---
title: -CLRHEADER |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /CLRHEADER
dev_langs:
- C++
helpviewer_keywords:
- -CLRHEADER dumpbin option
- /CLRHEADER dumpbin option
- CLRHEADER dumpbin option
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f6cda2f03e8a0473d2c45f54c96ca97b043d80d5
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704442"
---
# <a name="clrheader"></a>/CLRHEADER

CLR に固有の情報を表示します。

## <a name="syntax"></a>構文

> /CLRHEADER*ファイル*

### <a name="arguments"></a>引数

|||
|-|-|
*file*| ビルドされたイメージ ファイル[/clr](../../build/reference/clr-common-language-runtime-compilation.md)です。

## <a name="remarks"></a>コメント

**/CLRHEADER**マネージ プログラムで使用される .NET ヘッダーに関する情報を表示します。 出力は、.NET ヘッダーとヘッダー内のセクションのバイト単位のサイズと場所を示しています。

のみ、 [/HEADERS](../../build/reference/headers.md) DUMPBIN オプションはにより生成されるファイルで使用できるよう、 [/GL](../../build/reference/gl-whole-program-optimization.md)コンパイラ オプション。

ときに **/CLRHEADER**使用/clr でコンパイルされたファイルが生じることがあります、 **clr ヘッダー:** dumpbin 出力」セクション。 値**フラグ**どの/clr オプションを使用したことを示します。

- 0--/clr (イメージは、ネイティブ コードを含めることがあります)。

共通言語ランタイムのイメージをビルドしたかどうかもプログラムで確認できます。  詳細については、次を参照してください。[する方法: イメージがネイティブ モードまたは CLR 決定](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md)です。

**/Clr: 純粋な**と **/clr:safe**コンパイラ オプションが Visual Studio 2015 では廃止され、Visual Studio 2017 でサポートされていません。 「純粋」または「安全」にする必要があるコードは、c# に移植する必要があります。

## <a name="see-also"></a>関連項目

- [DUMPBIN オプション](../../build/reference/dumpbin-options.md)
