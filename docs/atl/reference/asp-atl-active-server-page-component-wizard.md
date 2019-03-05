---
title: ASP、ATL Active Server Page コンポーネント ウィザード
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.asp.asp
helpviewer_keywords:
- ATL Active Server Page Component Wizard, ASP
ms.assetid: 4d8cafd6-5e12-4461-8911-29288896af3c
ms.openlocfilehash: efc82edf00a9bb2f2facbd883ef88f1d093e0133
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57290197"
---
# <a name="asp-atl-active-server-page-component-wizard"></a>ASP、ATL Active Server Page コンポーネント ウィザード

ATL Active Server Page コンポーネント ウィザードのこのページを使用すると、情報と、ASP のコンポーネントに関連するのに状態を処理するためのオプションの設定を指定できます。

- **省略可能なメソッド**

   オプションの ASP メソッドを追加します。 **OnStartPage**と**OnEndPage**、オブジェクトにします。 Active Server Pages 組み込みオブジェクトを設定するのには、このオプションを選択する必要があります。 既定で選択されます。

- **OnStartPage/OnEndPage**

   [OnStartPage](https://msdn.microsoft.com/library/ms691624.aspx)スクリプトが、オブジェクトにアクセスしようとしています。 最初に呼び出されます。 **OnEndPage**オブジェクトが完了したときに呼び出されるスクリプトを処理します。

- **組み込みオブジェクト**

   選択する必要があります、 **OnStartPage/OnEndPage** ASP 組み込みオブジェクトを設定するオプション。

|オプション|説明|
|------------|-----------------|
|**要求**|組み込みの Active Server Pages へアクセスを提供**要求**オブジェクト。 要求オブジェクトは、HTTP 要求を渡すために使用されます。|
|**応答**|組み込みの Active Server Pages へアクセスを提供**応答**オブジェクト。 要求に応答してでは、応答オブジェクトは、ユーザーに表示するブラウザーに情報を送信します。|
|**セッション**|組み込みの Active Server Pages へアクセスを提供**セッション**オブジェクト。 **セッション**オブジェクトを格納する、状態情報の取得など、現在のユーザー セッションに関する情報を保持します。|
|**アプリケーション**|組み込みの Active Server Pages へアクセスを提供**アプリケーション**オブジェクト。 **アプリケーション**オブジェクトは複数の ASP オブジェクトで共有されている状態を管理します。|
|**サーバー**|組み込みの Active Server Pages へアクセスを提供**Server**オブジェクト。 **Server**オブジェクトでは、他の ASP オブジェクトを作成できます。|

## <a name="see-also"></a>関連項目

[ATL Active Server Page コンポーネント ウィザード](../../atl/reference/atl-active-server-page-component-wizard.md)<br/>
[ATL Active Server Page コンポーネント](../../atl/reference/adding-an-atl-active-server-page-component.md)
