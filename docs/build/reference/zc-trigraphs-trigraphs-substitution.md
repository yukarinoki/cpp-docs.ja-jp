---
title: /Zc:trigraphs (トライグラフの置換)
ms.date: 03/06/2018
f1_keywords:
- /Zc:trigraphs
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Conformance compiler options
- Zc compiler options (C++)
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
ms.openlocfilehash: 0e4c98e09551d39e3ff7978767b21f1d2c5bb318
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438657"
---
# <a name="zctrigraphs-trigraphs-substitution"></a>/Zc:trigraphs (トライグラフの置換)

**/Zc: トライグラフ**が指定されている場合、コンパイラは、対応する区切り記号を使用して、トライグラフ文字シーケンスを置き換えます。

## <a name="syntax"></a>構文

> **/Zc: トライグラフ**[ **-** ]

## <a name="remarks"></a>コメント

*トライグラフ*は、2つの連続する疑問符 ("??") とそれに続く一意の3番目の文字で構成されます。 C 言語標準では、一部の区切り文字に対して便利なグラフィック表現が含まれていない文字セットを使用するソースファイルのトライグラフがサポートされています。 たとえば、トライグラフが有効になっている場合、コンパイラは "??= "トライグラフ (' # ' 文字を使用した)。 C++ 14 までは、トライグラフは C のようにサポートされています。C++ 17 標準では、 C++言語からトライグラフが削除されます。 コードC++では、 **/zc: トライグラフ**コンパイラオプションを使用すると、トライグラフシーケンスを対応する区切り記号で置き換えることができます。 **/Zc: トライグラフ-** トライグラフの置換を無効にします。

**/Zc: トライグラフ**オプションは既定ではオフになっており、 [/permissive-](permissive-standards-conformance.md)オプションが指定されている場合、オプションは影響を受けません。

C/C++トライグラフの一覧と、トライグラフの使用方法を示す例については、[トライグラフ](../../c-language/trigraphs.md)を参照してください。

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関する記事を参照してください。

1. **[構成プロパティ]**  >  **[C/C++]**  >  **[コマンド ライン]** プロパティ ページを選択します。

1. **/Zc: トライグラフ**または **/zc: トライグラフ**が含まれるように "**追加オプション**" プロパティを変更し、[ **OK]** をクリックします。

## <a name="see-also"></a>参照

[/Zc (準拠)](zc-conformance.md)<br/>
[トライグラフ](../../c-language/trigraphs.md)<br/>
