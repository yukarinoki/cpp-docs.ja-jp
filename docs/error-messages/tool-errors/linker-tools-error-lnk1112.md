---
title: リンカ ツール エラー LNK1112 |Microsoft ドキュメント
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
ms.openlocfilehash: fd4af160607d75f036d25d21f5a95e753bddb3be
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1112"></a>リンカ ツール エラー LNK1112
モジュールのコンピューターの種類 'type1' は対象コンピューターの種類 'type2' と競合しています。  
  
 入力として指定されたオブジェクト ファイルは、別のコンピューターの種類用にコンパイルされています。  
  
 たとえば、 **/clr** でコンパイルされたオブジェクト ファイルを、 **/clr:pure** (コンピューターの種類 CEE) でコンパイルされたオブジェクト ファイルとリンクしようとした場合、リンカーはエラー LNK1112 を生成します。  
  
 同様に、 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] コンパイラを使用して 1 つのモジュールを作成し、x86 コンパイラを使用して別のモジュールを作成して、それらをリンクしようとすると、リンカーが LNK1112 を生成します。  
  
 このエラーの原因としては、64 ビット アプリケーションを開発しているのに、Visual C++ の 64 ビット コンパイラをインストールしていない可能性があります。 この場合は、64 ビットの構成は使用できません。 この問題を修正するには、Visual Studio のインストーラーを実行し、不足している C++ コンポーネントをインストールします。  
  
 このエラーは、 **構成マネージャー** の **アクティブ ソリューション構成** を変更する場合にも発生する可能性があり、その場合は中間出力ファイルを削除する前にプロジェクトのビルドを試行します。 このエラーを解決するには、 **[ビルド]** メニューから **[ソリューションのリビルド]** を選択します。 **[ビルド]** メニューから **[ソリューションのクリーン]** を選択して、ソリューションをビルドすることもできます。  
  
## <a name="see-also"></a>関連項目  
 [リンカー ツール エラーと警告](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)