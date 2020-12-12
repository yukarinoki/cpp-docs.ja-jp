---
description: '詳細情報: ASP、ATL Active Server ページコンポーネントウィザード'
title: ASP、ATL Active Server Page コンポーネント ウィザード
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.asp.asp
helpviewer_keywords:
- ATL Active Server Page Component Wizard, ASP
ms.assetid: 4d8cafd6-5e12-4461-8911-29288896af3c
ms.openlocfilehash: e9cc11cf60c3a87d6891c98a72eb240729d1a739
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165538"
---
# <a name="asp-atl-active-server-page-component-wizard"></a>ASP、ATL Active Server Page コンポーネント ウィザード

ATL Active Server ページコンポーネントウィザードのこのページを使用して、ASP コンポーネントに関連する情報および状態を処理するためのオプションの設定を指定します。

- **省略可能なメソッド**

   オプションの ASP メソッド **OnStartPage** と **OnEndPage** をオブジェクトに追加します。 Active Server ページの組み込みオブジェクトを設定するには、このオプションを選択する必要があります。 既定では、これが選択されています。

- **OnStartPage/OnEndPage**

   [OnStartPage](/previous-versions//ms691624\(v=vs.85\)) は、スクリプトがオブジェクトに初めてアクセスしようとしたときに呼び出されます。 **OnEndPage** は、オブジェクトがスクリプトの処理を終了したときに呼び出されます。

- **組み込みオブジェクト**

   ASP 組み込みオブジェクトを設定するには、 **OnStartPage/OnEndPage** オプションを選択する必要があります。

|オプション|説明|
|------------|-----------------|
|**Request**|Active Server Pages 組み込み **要求** オブジェクトへのアクセスを提供します。 要求オブジェクトは、HTTP 要求を渡すために使用されます。|
|**Response**|Active Server Pages 固有の **応答** オブジェクトへのアクセスを提供します。 要求に応答して、応答オブジェクトはブラウザーに情報を送信してユーザーに表示します。|
|**セッション**|Active Server Pages 固有の **セッション** オブジェクトへのアクセスを提供します。 **セッション** オブジェクトは、状態情報の格納や取得など、現在のユーザーセッションに関する情報を保持します。|
|**アプリケーション**。|Active Server Pages 組み込み **アプリケーション** オブジェクトへのアクセスを提供します。 **アプリケーション** オブジェクトは、複数の ASP オブジェクト間で共有される状態を管理します。|
|**サーバー**|Active Server Pages 組み込み **サーバー** オブジェクトへのアクセスを提供します。 **サーバー** オブジェクトを使用すると、他の ASP オブジェクトを作成できます。|

## <a name="see-also"></a>関連項目

[ATL Active Server Page コンポーネント ウィザード](../../atl/reference/atl-active-server-page-component-wizard.md)<br/>
[ATL Active Server Page コンポーネント](../../atl/reference/adding-an-atl-active-server-page-component.md)
