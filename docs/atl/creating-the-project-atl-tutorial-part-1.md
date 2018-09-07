---
title: プロジェクトの作成 (ATL チュートリアル、パート 1) |Microsoft Docs
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
ms.openlocfilehash: 54b45ff8c7af8c8aaf7232cefa2bb4f002fc37be
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755619"
---
# <a name="creating-the-project-atl-tutorial-part-1"></a>プロジェクトの作成 (ATL チュートリアル、パート 1)

このチュートリアルでは、属性なしの ATL プロジェクト多角形を表示する ActiveX オブジェクトを作成する手順について説明します。 オブジェクトには、多角形、およびコードの表示を更新する辺の数を変更するユーザーを許可するためのオプションが含まれています。

> [!NOTE]
>  ATL および MFC は一般にサポートされていません Visual Studio の Express edition でします。

> [!NOTE]
>  このチュートリアルでは、多角形のサンプルと同じソース コードを作成します。 ソース コードを手動で入力しないようにする場合をからダウンロードできます、[多角形サンプル抽象](../visual-cpp-samples.md)します。 「チュートリアル、またはそれを使用して、独自のプロジェクトのエラーを確認すると、多角形のソース コードにし、参照できます。

### <a name="to-create-the-initial-atl-project-using-the-atl-project-wizard"></a>ATL プロジェクト ウィザードを使用して、初期の ATL プロジェクトを作成するには

1. Visual Studio 開発環境で次のようにクリックします。**新規**上、**ファイル** メニューをクリック**プロジェクト**します。

2. をクリックして、 **Visual C プロジェクト**フォルダーと選択**ATL プロジェクト**します。

3. 型*多角形*プロジェクト名として。

     My documents \visual Studio プロジェクトでは、ソース コードの場所は既定では、通常、新しいフォルダーが自動的に作成されます。

4. をクリックして**OK**し、ATL プロジェクト ウィザードを開きます。

5. クリックして**アプリケーション設定**に使用できるオプションを参照してください。

6. コントロールを作成すると、コントロールは、インプロセス サーバーである必要がありますのままにして、**アプリケーションの種類**DLL として。

7. 既定値では、その他のオプションのままにし、をクリックして**完了**します。

ATL プロジェクト ウィザードでは、いくつかのファイルを生成することによって、プロジェクトを作成します。 多角形のオブジェクトを展開して、ソリューション エクスプ ローラーでこれらのファイルを表示できます。 ファイルは、以下に示します。

|ファイル|説明|
|----------|-----------------|
|Polygon.cpp|実装を含む`DllMain`、 `DllCanUnloadNow`、 `DllGetClassObject`、 `DllRegisterServer`、および`DllUnregisterServer`します。 また、プロジェクトで ATL オブジェクトの一覧であるオブジェクト マップが含まれます。 これは、最初は空です。|
|Polygon.def|このモジュール定義ファイルでは、DLL に必要なエクスポートに関する情報をリンカーを提供します。|
|Polygon.idl|インターフェイス定義言語ファイル、オブジェクトに固有のインターフェイスについて説明します。|
|Polygon.rgs|このレジストリ スクリプトには、プログラムの DLL を登録するための情報が含まれています。|
|Polygon.rc|最初にバージョン情報と、プロジェクト名を含む文字列を含むリソース ファイル。|
|Resource.h|リソース ファイルのヘッダー ファイルです。|
|Polygonps.def|このモジュール定義ファイルでは、リンカーがアパートメント間呼び出しをサポートするプロキシとスタブのコードに必要なエクスポートに関する情報を提供します。|
|stdafx.cpp|ファイル`#include`ATL 実装ファイルです。|
|stdafx.h|ファイル`#include`ATL ヘッダー ファイル。|

1. ソリューション エクスプ ローラーで右クリックし、`Polygon`プロジェクト。

2. ショートカット メニューで、**プロパティ**します。

3. をクリックして**リンカー**します。 変更、 **UserRedirection あたり**オプションを**はい**します。

4. **[OK]** をクリックします。

次の手順では、プロジェクトに、コントロールを追加します。

[手順 2 に](../atl/adding-a-control-atl-tutorial-part-2.md)

## <a name="see-also"></a>関連項目

[チュートリアル](../atl/active-template-library-atl-tutorial.md)
