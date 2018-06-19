---
title: /Zc:trigraphs (トライグラフの置換) |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Conformance compiler options
- Zc compiler options (C++)
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3e465b62944b360d6fdb09da1230f3353658437b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379872"
---
# <a name="zctrigraphs-trigraphs-substitution"></a>/Zc:trigraphs (トライグラフの置換)

ときに **/Zc:trigraphs**を指定すると、コンパイラは、対応する区切り文字を使用して、トライグラフ文字シーケンスを置き換えます。

## <a name="syntax"></a>構文

> **/Zc:trigraphs**[**-**]  

## <a name="remarks"></a>コメント

A*トライグラフ*2 つの連続する疑問符で構成されます ("??") によって一意の 3 番目の文字の後にします。 標準の C 言語では、いくつかの区切り文字の適切なグラフィック表示が含まれない文字セットを使用するソース ファイルのトライグラフをサポートします。 たとえば、トライグラフを有効にすると、コンパイラが置き換えられます、"[概要] タブ。="トライグラフ '#' 文字を使用しています。 C. と同様に c++ 14、を通じてトライグラフのサポートします。標準の c++ 17 では、C の言語からトライグラフを削除します。 C++ コードで、 **/Zc:trigraphs**コンパイラ オプション、対応する区切り文字でトライグラフ シーケンスの置換を有効にします。 **/Zc:trigraphs-** トライグラフの置換を無効にします。

**/Zc:trigraphs**オプションは既定では、オフと、オプションが場合の影響を受ける、[寛容/-](permissive-standards-conformance.md)オプションを指定します。

C と C++ トライグラフとトライグラフを使用する方法を示す例の一覧は、次を参照してください。[トライグラフ](../../c-language/trigraphs.md)です。

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 変更、**追加オプション**含めるプロパティを **/Zc:trigraphs**または **/Zc:trigraphs-** を選択し**OK**です。

## <a name="see-also"></a>関連項目

[/Zc (準拠)](../../build/reference/zc-conformance.md)<br/>
[トライグラフ](../../c-language/trigraphs.md)<br/>
