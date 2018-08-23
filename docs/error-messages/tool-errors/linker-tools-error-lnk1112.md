---
title: リンカ ツール エラー LNK1112 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1112
dev_langs:
- C++
helpviewer_keywords:
- LNK1112
ms.assetid: 425793d8-37e6-4072-9b6e-c3d4e9c12562
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e08e8dae82675d9503575d543edfcaa2c96275e9
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42539317"
---
# <a name="linker-tools-error-lnk1112"></a>リンカ ツール エラー LNK1112

> マシンの種類のモジュール '*type1*'対象コンピューターの種類は'*type2*'

## <a name="remarks"></a>Remarks

入力として指定されたオブジェクト ファイルは、別のコンピューターの種類用にコンパイルされています。

たとえば、 **/clr** でコンパイルされたオブジェクト ファイルを、 **/clr:pure** (コンピューターの種類 CEE) でコンパイルされたオブジェクト ファイルとリンクしようとした場合、リンカーはエラー LNK1112 を生成します。 **/Clr: 純粋な**コンパイラ オプションは Visual Studio 2015 で非推奨とされ、Visual Studio 2017 でサポートされていません。

同様に、x64 の 1 つのモジュールを作成する場合コンパイラおよび x86 と別のモジュール コンパイラ、およびそれらをリンクしようと、リンカーが LNK1112 を生成します。

このエラーの原因としては、64 ビット アプリケーションを開発しているのに、Visual C++ の 64 ビット コンパイラをインストールしていない可能性があります。 この場合は、64 ビットの構成は使用できません。 この問題を修正するには、Visual Studio のインストーラーを実行し、不足している C++ コンポーネントをインストールします。

このエラーは、 **構成マネージャー** の **アクティブ ソリューション構成** を変更する場合にも発生する可能性があり、その場合は中間出力ファイルを削除する前にプロジェクトのビルドを試行します。 このエラーを解決するには、 **[ビルド]** メニューから **[ソリューションのリビルド]** を選択します。 **[ビルド]** メニューから **[ソリューションのクリーン]** を選択して、ソリューションをビルドすることもできます。

## <a name="see-also"></a>関連項目

- [リンカー ツール エラーと警告](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)
