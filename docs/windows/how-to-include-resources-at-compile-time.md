---
title: '方法: コンパイル時にリソースをインクルード |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vs.resvw.resource.including
- vc.resvw.resource.including
dev_langs:
- C++
helpviewer_keywords:
- compiling source code, including resources
- comments [C++], compiled files
- resources [Visual Studio], including at compile time
- projects [C++], including resources
- '#include directive'
- include directive (#include)
ms.assetid: 357e93c2-0a29-42f9-806f-882f688b8924
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 28374482abd5d2e039c92adbd34f261bdc259b9d
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018917"
---
# <a name="how-to-include-resources-at-compile-time"></a>方法: コンパイル時にリソースをインクルードする
一般的に、1 つのリソース スクリプト (.rc) ファイルですべてのリソースの既定の設定を操作することは、簡単かつ便利なやり方です。 ただし、追加できますリソースその他のファイルで、現在のプロジェクトにコンパイル時にリストにすることによって、**コンパイル時ディレクティブ**ボックスに、[リソース インクルード ダイアログ ボックス](../windows/resource-includes-dialog-box.md)します。  
  
 メインの .rc ファイル以外のファイルにリソースを配置する理由のいくつかを次に示します。  
  
-   リソース ステートメントに、.rc ファイルを保存するときに削除されないコメントを追加する。  
  
     リソース エディター直接読み取りません .rc または`resource.h`ファイル。 リソース コンパイラがこれらのファイルをコンパイルして、リソース エディターで使用される .aps ファイルにします。 これはコンパイル手順のファイルで、シンボル データのみが格納されます。 通常のコンパイル プロセスと同様に、シンボル以外の情報 (コメントなど) はコンパイル プロセス中に破棄されます。 .Rc ファイルを再生成するたびに .aps ファイルを取得、.rc ファイルとの同期、(たとえば、保存すると、リソース エディターを上書き、.rc ファイルと`resource.h`ファイル)。 リソース自体に対する変更は .rc ファイルに組み込まれたままですが、コメントは .rc ファイルが上書きされると失われます。  
  
-   開発とテストが既に完了している、さらに変更する必要のないリソースをインクルードする。 (インクルードされるファイルのうち、.rc 拡張子を持たないファイルは、リソース エディターで編集できません)。  
  
-   複数の異なるプロジェクトで使用されるリソースや、ソース コードのバージョン管理システムの一部であり、変更がすべてのプロジェクトに影響する中央の場所に存在する必要があるリソースをインクルードする。  
  
-   カスタム形式のリソース (たとえば、RCDATA リソース) をインクルードする。 RCDATA リソースには、特別な要件があります。 たとえば、nameID フィールドの値として式を使用することはできません。 詳細については、[!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)] のドキュメントを参照してください。  
  
 セクションでは、1 つに配置してこれらの条件のいずれかを満たす既存の .rc ファイルにセクションがある場合または別個の .rc ファイルの詳細、およびそれらを使用して、プロジェクトに含める、 [] ダイアログ ボックスの [リソース インクルード](../windows/resource-includes-dialog-box.md)します。 *Projectname*新しいプロジェクトの \res サブディレクトリに作成された .rc2 ファイルはこの目的に使用します。  
  
### <a name="to-include-resources-in-your-project-at-compile-time"></a>コンパイル時にリソースをインクルードするには  
  
1.  一意のファイル名を持つリソース スクリプト ファイルにリソースを配置します。 使用しない*projectname*.rc、メイン リソース スクリプト ファイルを使用するファイル名です。  
  
2.  .Rc ファイルを右クリックして (で[リソース ビュー](../windows/resource-view-window.md)) 選択**リソース ファイルのインクルード**ショートカット メニューから。  
  
3.  **コンパイル時ディレクティブ**ボックスで、追加、 [#include](../preprocessor/hash-include-directive-c-cpp.md)開発環境で、メイン リソース ファイルで新しいリソース ファイルをインクルードします。  
  
     この方法でインクルードされるリソースは、コンパイル時に実行可能ファイルの一部になります。 これらのリソースは、プロジェクトのメイン .rc ファイルを操作しているときに編集または変更の対象として直接操作できません。 インクルードされる .rc ファイルを別個に開く必要があります。 インクルードされるファイルのうち、.rc 拡張子を持たないファイルは、リソース エディターで編集できません。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [リソース ファイル (Visual Studio)](../windows/resource-files-visual-studio.md)   
 [リソース エディター](../windows/resource-editors.md)