---
title: プロジェクトのビルドの警告 PRJ0049 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- PRJ0049
ms.assetid: 8b38afa1-e080-4efd-ae89-776cfd044413
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8df6fcb8bc5d6517a46279e0bef5036db1e81241
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33319811"
---
# <a name="project-build-warning-prj0049"></a>プロジェクト ビルドの警告 PRJ0049
参照先の対象 '\<参照 >'.NET Framework が必要\<ごと > とは、このプロジェクトのターゲット フレームワーク上で実行できません  
  
 Visual Studio 2008 を使用して作成されたアプリケーションのバージョンを指定できます、[!INCLUDE[dnprdnshort](../../error-messages/tool-errors/includes/dnprdnshort_md.md)]対象にできる必要があります。 アセンブリまたはプロジェクトのバージョンに依存しているへの参照を追加する場合、[!INCLUDE[dnprdnshort](../../error-messages/tool-errors/includes/dnprdnshort_md.md)]ですが、対象のバージョンよりも後、コンパイル時にこの警告が表示されます。  
  
### <a name="to-correct-this-warning"></a>この警告を解決するには  
  
1.  次のいずれかを選択します。  
  
    -   プロジェクトの対象となるフレームワークを変更して**プロパティ ページ** ダイアログ ボックスのすべての参照先アセンブリとプロジェクトの最小限の framework のバージョン以降であるようにします。 詳細については、次を参照してください。[参照の追加](../../ide/adding-references-in-visual-cpp-projects.md)です。  
  
    -   アセンブリまたは最小限の framework バージョンが、対象の framework よりも後のプロジェクトへの参照を削除します。 これらの項目は、プロジェクトの警告アイコンでマークする**プロパティ ページ**です。  
  
## <a name="see-also"></a>関連項目  
 [プロジェクト ビルド エラーと警告 (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)