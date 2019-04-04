---
title: リンカ ツール エラー LNK1309
ms.date: 11/04/2016
f1_keywords:
- LNK1309
helpviewer_keywords:
- LNK1309
ms.assetid: 10146071-883f-4849-97d1-c7468f90efbb
ms.openlocfilehash: ea675ca835dfc3fe4881e5fabbea746a4442b10a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499030"
---
# <a name="linker-tools-error-lnk1309"></a>リンカ ツール エラー LNK1309

> *type1*モジュールが検出されましたで無効なスイッチ/CLRIMAGETYPE:*type2。*

## <a name="remarks"></a>Remarks

CLR イメージの種類が要求されました **/CLRIMAGETYPE**が 1 つまたは複数のモジュールは、その型と互換性がないので、リンカーはその種類のイメージを作成できませんでした。

指定した場合に LNK1309 が表示されます、 **/CLRIMAGETYPE:safe**でビルドされたモジュールを渡す **/clr: 純粋な**します。

**/Clr: 純粋な**と **/clr:safe**コンパイラ オプションおよびサポート ライブラリは Visual Studio 2015 で非推奨とされ、Visual Studio 2017 でサポートされていません。

[D] ptrustu .lib を使用して、部分的に信頼された CLR 純粋なアプリケーションをビルドしようとした場合は、LNK1309 も表示されます。 部分的に信頼されたアプリケーションを作成する方法については、[方法: CRT ライブラリ DLL の依存関係の削除によって部分的に信頼されたアプリケーションを作成する](../../dotnet/create-a-partially-trusted-application.md)を参照してください。

詳細については、[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)と[/CLRIMAGETYPE (型の CLR イメージの指定)](../../build/reference/clrimagetype-specify-type-of-clr-image.md)を参照してください。