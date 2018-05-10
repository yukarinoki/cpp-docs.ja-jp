---
title: プロジェクトとソリューション ファイル |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.files.projectandsolution
dev_langs:
- C++
helpviewer_keywords:
- project files [C++]
- file types [C++], makefiles
- .sdf, browsing database file
- Makefile projects
- browsing database file, .sdf
- file types [C++], project files
ms.assetid: 5823b954-36cf-42d3-8fd5-25bab3ef63d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 08cf1386ef177823c37bc285392309ec47f3c464
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="project-and-solution-files"></a>プロジェクト ファイルとソリューション ファイル
Visual Studio でプロジェクトを作成すると、以下のファイルが作成されます。 これらのファイルは、ソリューション内のプロジェクト ファイルを管理するために使用されます。  
  
|ファイル名|ディレクトリの場所|ソリューション エクスプローラーでの場所|説明|  
|--------------|------------------------|--------------------------------|-----------------|  
|*Solname*.sln|*Projname*|ソリューション エクスプローラーでは非表示|*ソリューション*ファイル。 1 つまたは複数のプロジェクトのすべての要素を 1 つのソリューションにまとめます。|  
|*Projname*.suo|*Projname*|ソリューション エクスプローラーでは非表示|*ソリューション オプション*ファイル。 ソリューションのカスタマイズを格納します。これにより、ソリューション内のプロジェクトまたはファイルを開くたびに、指定した外観や動作が再現されます。|  
|*Projname*.vcxproj|*Projname*|ソリューション エクスプローラーでは非表示|*プロジェクト*ファイル。 各プロジェクトに固有の情報を格納します  (以前のバージョンでこのファイルの名前が*Projname*.vcproj または*Projname*.dsp)。Visual C プロジェクト ファイルの例は、次を参照してください。[プロジェクトファイル](../ide/project-files.md)です。|  
|*Projname*.vcxitems|*Projname*|ソリューション エクスプローラーでは非表示|*共有アイテム プロジェクト*ファイル。 このプロジェクトはビルドされません。  代わりに、プロジェクトを別の C++ プロジェクトから参照できるし、そのファイルは、参照元のプロジェクトのビルド プロセスの一部になります。 クロスプラット フォーム C++ プロジェクトで共通コードを共有するために使用できます。|
|*Projname*.sdf|*Projname*|ソリューション エクスプローラーでは非表示|*参照データベース*ファイル。 などの参照とナビゲーション機能をサポート**定義へ移動**、**すべての参照の検索**、および**クラス ビュー**です。 このファイルは、ヘッダー ファイルの解析によって生成されます。|  
|*Projname です。*vcxproj.filters|*Projname*|ソリューション エクスプローラーでは非表示|*フィルター*ファイル。 ソリューションに追加されたファイルを配置する場所を指定します。 .H ファイルに追加するなど、**ヘッダー ファイル**ノード。|  
|*Projname です。*vcxproj.user|*Projname*|ソリューション エクスプローラーでは非表示|*移行ユーザー*ファイル。 プロジェクトが Visual Studio 2008 から移行された後、このファイルには .vsprops ファイルから変換された情報が格納されます。|  
|*Projname*.idl|*Projname*|ソース|(プロジェクトに固有) コントロール タイプ ライブラリのインターフェイス記述言語 (IDL) ソース コードが含まれます。 このファイルは、Visual C++ でタイプ ライブラリを生成するために使用されます。 生成されたライブラリは、他のオートメーション クライアントにコントロールのインターフェイスを公開します。 詳細については、次を参照してください。[インターフェイス定義 (IDL) ファイル](http://msdn.microsoft.com/library/windows/desktop/aa378712)Windows SDK に含まれています。|  
|Readme.txt|*Projname*|プロジェクト|*お読みください*ファイル。 アプリケーション ウィザードによって生成され、プロジェクト内のファイルについて記述します。|  
  
## <a name="see-also"></a>関連項目  
 [Visual C++ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)