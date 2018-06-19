---
title: プロジェクト (ATL チュートリアル、パート 1) を作成する |Microsoft ドキュメント
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f6b727d1-390a-4b27-b82f-daadcd9fc059
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1aedf7b4112d4c8d4bb5b2a174e93925f5a46ce5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357719"
---
# <a name="creating-the-project-atl-tutorial-part-1"></a>プロジェクトの作成 (ATL チュートリアル、パート 1)
このチュートリアルでは、属性なしの ATL プロジェクトを多角形を表示する ActiveX オブジェクトを作成する手順について説明します。 オブジェクトには、辺の多角形、およびコードの表示を更新数を変更するユーザーを許可するためのオプションが含まれています。  
  
> [!NOTE]
>  ATL および MFC は一般にサポートされていません Visual Studio の Express edition でします。  
  
> [!NOTE]
>  このチュートリアルでは、多角形のサンプルと同じソース コードを作成します。 ソース コードを手動で入力しないようにする場合をからダウンロードできます、[多角形サンプル抽象](../visual-cpp-samples.md)です。 「チュートリアル、または独自のプロジェクトでのエラー チェックを使用すると、多角形のソース コードを参照し、できます。  
  
### <a name="to-create-the-initial-atl-project-using-the-atl-project-wizard"></a>ATL プロジェクト ウィザードを使用して初期 ATL プロジェクトを作成するには  
  
1.  Visual Studio 開発環境でをクリックして**新規**上、**ファイル** メニューをクリックして**プロジェクト**です。  
  
2.  クリックして、 **Visual C プロジェクト**フォルダーと選択**ATL プロジェクト**です。  
  
3.  型`Polygon`プロジェクト名として。  
  
     My documents \visual Studio プロジェクトでは、ソース コードの場所は既定で通常と、新しいフォルダーを自動的に作成されます。  
  
4.  をクリックして**OK**と ATL プロジェクト ウィザードが開きます。  
  
5.  をクリックして**アプリケーション設定**使用可能なオプションを表示します。  
  
6.  コントロールを作成すると、コントロールは、インプロセス サーバーである必要がありますのままにして、**アプリケーションの種類**DLL として。  
  
7.  その既定値で、他のオプションのままにし、をクリックして**完了**です。  
  
 ATL プロジェクト ウィザードでは、いくつかのファイルを生成することによって、プロジェクトを作成します。 ソリューション エクスプ ローラーでこれらのファイルを表示するには、Polygon オブジェクトを展開します。 ファイルは次のとおりです。  
  
|ファイル|説明|  
|----------|-----------------|  
|Polygon.cpp|実装を含む`DllMain`、 `DllCanUnloadNow`、 `DllGetClassObject`、 `DllRegisterServer`、および`DllUnregisterServer`です。 オブジェクト マップは、あるプロジェクトで ATL オブジェクトの一覧も含まれています。 これは、最初は空です。|  
|Polygon.def|このモジュール定義ファイルは、リンカーが、DLL で必要なエクスポートに関する情報を提供します。|  
|Polygon.idl|インターフェイス定義言語ファイル、オブジェクト固有のインターフェイスを記述します。|  
|Polygon.rgs|このレジストリ スクリプトには、プログラムの DLL を登録するための情報が含まれています。|  
|Polygon.rc|最初にバージョン情報と、プロジェクト名を含む文字列を含むリソース ファイル。|  
|Resource.h|リソース ファイルのヘッダー ファイル。|  
|Polygonps.def|このモジュール定義ファイルは、アパートメント間で呼び出しをサポートするプロキシとスタブのコードに必要なエクスポートに関する情報をリンカーを提供します。|  
|stdafx.cpp|ファイル`#include`ATL 実装ファイル。|  
|stdafx.h|ファイル`#include`ATL ヘッダー ファイルです。|  
  
1.  ソリューション エクスプ ローラーで右クリックし、`Polygon`プロジェクト。  
  
2.  ショートカット メニューをクリックして**プロパティ**です。  
  
3.  をクリックして**リンカー**です。 変更、 **UserRedirection あたり**オプションを**はい**です。  
  
4.  **[OK]** をクリックします。  
  
 次の手順では、プロジェクトに、コントロールを追加します。  
  
 [手順 2 に](../atl/adding-a-control-atl-tutorial-part-2.md)  
  
## <a name="see-also"></a>関連項目  
 [チュートリアル](../atl/active-template-library-atl-tutorial.md)

