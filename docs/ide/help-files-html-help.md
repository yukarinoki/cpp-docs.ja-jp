---
title: ヘルプ ファイル (HTML ヘルプ) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- file types [C++], HTML Help files
ms.assetid: d30a1b1b-318f-4a78-8b60-93da53a224a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d180fe4f9cf1baf26b27423ffda975bfe0fe85ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="help-files-html-help"></a>ヘルプ ファイル (HTML ヘルプ)
選択して、アプリケーションにヘルプのサポートの HTML ヘルプの種類を追加するときに、次のファイルが作成された、**状況依存のヘルプ** チェック ボックスをクリックして**HTML ヘルプ形式**で[高度な機能](../mfc/reference/advanced-features-mfc-application-wizard.md)MFC アプリケーション ウィザードのページです。  
  
|ファイル名|ディレクトリの場所|ソリューション エクスプローラーでの場所|説明|  
|---------------|------------------------|--------------------------------|-----------------|  
|*Projname*.hhp|*Projname*\hlp|HTML ヘルプ ファイル|ヘルプ プロジェクト ファイル。 .Hxs ファイルにヘルプ ファイルまたは .chm ファイルをコンパイルに必要なデータが含まれています。|  
|*Projname*.hhk|*Projname*\hlp|HTML ヘルプ ファイル|ヘルプ トピックのインデックスが含まれています。|  
|*Projname*影響|*Projname*\hlp|HTML ヘルプ ファイル|ヘルプ プロジェクトの内容。|  
|Makehtmlhelp.bat|*Projname*|ソース ファイル|プロジェクトがコンパイルされるときにヘルプ プロジェクトをビルドするシステムで使用します。|  
|Afxcore.htm|*Projname*\hlp|HTML ヘルプ トピック|MFC の標準のコマンドと画面オブジェクトの標準のヘルプ トピックが含まれています。 このファイルに独自のヘルプ トピックを追加します。|  
|Afxprint.htm|*Projname*\hlp|HTML ヘルプ トピック|印刷コマンドのヘルプ トピックが含まれています。|  
|*.jpg です。\*.gif|*Projname*\hlp\Images|リソース ファイル (Visual Studio)|生成されたヘルプ トピックについてはファイルのイメージが含まれます。|  
  
## <a name="see-also"></a>関連項目  
 [Visual C++ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)