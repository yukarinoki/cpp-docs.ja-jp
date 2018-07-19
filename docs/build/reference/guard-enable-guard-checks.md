---
title: ガード (ガード チェックを有効にする) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 72758e23-70ac-4616-94d7-d767477406d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d05dd4f9d213c3d2729459486a9d0cfdbd79110
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375257"
---
# <a name="guard-enable-guard-checks"></a>/GUARD (ガード チェックを有効にする)
実行可能イメージで、Control Flow Guard のチェックのサポートを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
/GUARD:{CF|NO}  
```  
  
## <a name="remarks"></a>コメント  
 /GUARD:CF を指定した場合、リンカーは、Control Flow Guard (CFG) の実行時チェックをサポートしていることを示すように、.dll または .exe のヘッダーを変更します。 また、リンカーは、必要な制御フローのターゲット アドレス データをヘッダーに追加します。 既定では、/GUARD:CF は無効です。 /GUARD:NO を使用して明示的に無効化できます。 有効にするには、/GUARD:CF も必要です、 [/DYNAMICBASE (使用するアドレス領域のレイアウトのランダム化)](../../build/reference/dynamicbase-use-address-space-layout-randomization.md)リンカー オプション、既定でオンになっています。  
  
 使用してソース コードをコンパイルするときに、 [/guard:cf](../../build/reference/guard-enable-control-flow-guard.md)可能なターゲット アドレスに対するすべての間接的な呼び出しを確認するにはオプション、コンパイラの分析、制御フロー。 コンパイラは、間接呼び出し命令のターゲット アドレスが、実行時に既知のターゲット アドレスの一覧にあることを検証するコードを挿入します。 CFG をサポートするオペレーティング システムは、CFG のランタイム チェックに失敗したプログラムを停止します。 これにより、データの破損を利用して呼び出し対象を変更することによって攻撃者が悪意のあるコードを実行することは、より難しくなります。  
  
 /GUARD:CF オプションは、CFG に対応する実行可能イメージを作成するために、コンパイラとリンカーの両方で指定する必要があります。 /GUARD:CF を使用してコンパイルされているもののリンクされていないコードでは、実行時チェックのコストが生じますが、CFG 保護を有効にしません。 /GUARD:CF オプションに指定した場合、 `cl` 1 つの手順では、コンパイラのコンパイルし、リンクするコマンドは、フラグをリンカーに渡します。 ときに、 **Control Flow Guard**プロパティは、Visual Studio の設定は、/GUARD:CF オプションは、コンパイラとリンカーの両方に渡されます。 オプションはで明示的に指定する必要がありますオブジェクト ファイルまたはライブラリは、個別にコンパイルされている、ときに、`link`コマンド。  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>このリンカー オプションを Visual Studio で設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  展開**構成プロパティ**、**リンカー**、**コマンドライン**です。  
  
3.  **追加オプション**、入力`/GUARD:CF`です。  
  
## <a name="see-also"></a>関連項目  
 [/guard (有効にする制御フロー ガードを)](../../build/reference/guard-enable-control-flow-guard.md)   
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)