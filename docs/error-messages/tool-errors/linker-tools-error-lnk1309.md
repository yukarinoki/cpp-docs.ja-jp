---
description: 詳細については、「リンカツール Error LNK1309」を参照してください。
title: リンカ ツール エラー LNK1309
ms.date: 11/04/2016
f1_keywords:
- LNK1309
helpviewer_keywords:
- LNK1309
ms.assetid: 10146071-883f-4849-97d1-c7468f90efbb
ms.openlocfilehash: e04498ae5226f748b6ba5cc2ce0cd9340f4547c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193644"
---
# <a name="linker-tools-error-lnk1309"></a>リンカ ツール エラー LNK1309

> *type1* モジュールが検出されました。スイッチ/CLRIMAGETYPE: 型が *無効です。*

## <a name="remarks"></a>解説

**/CLRIMAGETYPE** で CLR イメージ型が要求されましたが、1つ以上のモジュールがその型と互換性がないため、リンカーはその型のイメージを生成できませんでした。

たとえば、 **/CLRIMAGETYPE: safe** を指定し、 **/clr: pure** でビルドされたモジュールを渡すと、LNK1309 が表示されます。

**/Clr: pure** および **/clr: safe** コンパイラオプションとサポートライブラリは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

Ptrustu [d] .lib を使用して、部分的に信頼された CLR 純粋アプリケーションをビルドしようとすると、LNK1309 も表示されます。 部分的に信頼されたアプリケーションを作成する方法については、「 [方法: CRT ライブラリ DLL の依存関係を削除して部分信頼アプリケーションを作成](../../dotnet/create-a-partially-trusted-application.md)する」を参照してください。

詳細については、「 [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md) 」および「 [/CLRIMAGETYPE (Clr イメージの型の指定)](../../build/reference/clrimagetype-specify-type-of-clr-image.md)」を参照してください。
