---
title: /Zc:trigraphs (トライグラフの置換)
description: トライグラフの準拠サポートを制御する Microsoft C++ コンパイラオプション。
ms.date: 07/25/2020
f1_keywords:
- /Zc:trigraphs
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Conformance compiler options
- Zc compiler options (C++)
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
ms.openlocfilehash: e24f3d2f0064c3acc04b4c3774f47f6e442d5ddd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211854"
---
# <a name="zctrigraphs-trigraphs-substitution"></a>`/Zc:trigraphs`(トライグラフ置換)

を指定した場合 **`/Zc:trigraphs`** 、コンパイラは、対応する区切り記号を使用して、トライグラフの文字シーケンスを置き換えます。

## <a name="syntax"></a>構文

> **`/Zc:trigraphs`**[**`-`**]

## <a name="remarks"></a>解説

*トライグラフ*は、2つの連続する疑問符 ( **`??`** ) の後に一意の3番目の文字で構成されます。 C 言語標準では、一部の区切り文字に対して便利なグラフィック表現が含まれていない文字セットを使用するソースファイルのトライグラフがサポートされています。 たとえば、トライグラフが有効になっている場合、コンパイラは **`??=`** 文字を使用してトライグラフを置き換え **`#`** ます。 C++ 14 までは、トライグラフは C のようにサポートされています。C++ 17 標準では、C++ 言語からトライグラフが削除されます。 C++ コードでは、 **`/Zc:trigraphs`** コンパイラオプションを使用すると、トライグラフシーケンスを対応する区切り記号で置き換えることができます。 **`/Zc:trigraphs-`** トライグラフの置換を無効にします。

このオプションは **`/Zc:trigraphs`** 既定ではオフになっており、オプション [`/permissive-`](permissive-standards-conformance.md) が指定されている場合、オプションは影響を受けません。

C/c + + トライグラフの一覧と、トライグラフの使用方法を示す例については、[トライグラフ](../../c-language/trigraphs.md)を参照してください。

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. またはを含むように "**追加オプション**" プロパティを変更し、[ **`/Zc:trigraphs`** **`/Zc:trigraphs-`** **OK]** をクリックします。

## <a name="see-also"></a>関連項目

[`/Zc`互換性](zc-conformance.md)<br/>
[トライグラフ](../../c-language/trigraphs.md)
