---
title: プロジェクト ファイルとソリューション ファイル
ms.date: 05/06/2019
helpviewer_keywords:
- project files [C++]
- file types [C++], makefiles
- .sdf, browsing database file
- Makefile projects
- browsing database file, .sdf
- file types [C++], project files
ms.assetid: 5823b954-36cf-42d3-8fd5-25bab3ef63d9
ms.openlocfilehash: 153480331d3300555c78a3489ca603d854893f5b
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2019
ms.locfileid: "65446594"
---
# <a name="project-and-solution-files"></a>プロジェクト ファイルとソリューション ファイル

Visual Studio でプロジェクトを作成すると、以下のファイルが作成されます。 これらのファイルは、ソリューション内のプロジェクト ファイルを管理するために使用されます。

|ファイル名|ディレクトリの場所|ソリューション エクスプローラーでの場所|説明|
|--------------|------------------------|--------------------------------|-----------------|
|*Solname*.sln|*Projname*|ソリューション エクスプローラーでは非表示|*ソリューション* ファイル。 1 つまたは複数のプロジェクトのすべての要素を 1 つのソリューションにまとめます。|
|*Projname*.suo|*Projname*|ソリューション エクスプローラーでは非表示|*ソリューション オプション* ファイル。 ソリューションのカスタマイズを格納します。これにより、ソリューション内のプロジェクトまたはファイルを開くたびに、指定した外観や動作が再現されます。|
|*Projname*.vcxproj|*Projname*|ソリューション エクスプローラーでは非表示|*プロジェクト* ファイル。 各プロジェクトに固有の情報を格納します  (以前のバージョンでは、このファイルは *Projname*.vcproj または *Projname*.dsp という名前でした)。例については、C++プロジェクト ファイル (.vcxproj) を参照してください[プロジェクト ファイル](project-files.md)します。|
|*Projname*.vcxitems|*Projname*|ソリューション エクスプローラーでは非表示|*共有アイテム プロジェクト* ファイル。 このプロジェクトはビルドされません。  代わりに、プロジェクトを別の C++ プロジェクトで参照することができます。そのファイルは参照元プロジェクトのビルド プロセスの一部となります。 これは、クロスプラット フォームの C++ プロジェクトと共通コードを共有するために使用できます。|
|*Projname*.sdf|*Projname*|ソリューション エクスプローラーでは非表示|*参照データベース* ファイル。 **定義へ移動**、**すべての参照の検索**、**クラス ビュー**など、参照機能とナビゲーション機能をサポートします。 このファイルは、ヘッダー ファイルの解析によって生成されます。|
|*Projname*.vcxproj.filters|*Projname*|ソリューション エクスプローラーでは非表示|*フィルター* ファイル。 ソリューションに追加されたファイルを配置する場所を指定します。 たとえば、.h ファイルは **ヘッダー ファイル** ノードに配置されます。|
|*Projname*.vcxproj.user|*Projname*|ソリューション エクスプローラーでは非表示|*移行ユーザー* ファイル。 プロジェクトが Visual Studio 2008 から移行された後、このファイルには .vsprops ファイルから変換された情報が格納されます。|
|*Projname*.idl|*Projname*|ソース|(プロジェクトに固有) コントロール タイプ ライブラリのインターフェイス記述言語 (IDL) ソース コードが含まれます。 このファイルは、Visual C++ でタイプ ライブラリを生成するために使用されます。 生成されたライブラリは、他のオートメーション クライアントにコントロールのインターフェイスを公開します。 詳細については、Windows SDK の「[Interface Definition (IDL) File](/windows/desktop/Rpc/the-interface-definition-language-idl-file)」(インターフェイス定義 (IDL) ファイル) を参照してください。|
|Readme.txt|*Projname*|プロジェクト|*read me* ファイル。 アプリケーション ウィザードによって生成され、プロジェクト内のファイルについて記述します。|

## <a name="see-also"></a>関連項目

[ファイルのビジュアルの種類が作成されたC++プロジェクト](file-types-created-for-visual-cpp-projects.md)
