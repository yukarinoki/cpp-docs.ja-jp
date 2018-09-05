---
title: オプション、ATL シンプル オブジェクト ウィザード |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.simple.options
dev_langs:
- C++
helpviewer_keywords:
- ATL Simple Object Wizard, options
ms.assetid: 125fe179-942d-4181-8b82-33e92e1fd779
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f34b5598380c5413caecd6f9f52ca5ad9fb57bd0
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43764908"
---
# <a name="options-atl-simple-object-wizard"></a>オプション、ATL シンプル オブジェクト ウィザード

効率の向上およびオブジェクトのエラーのサポートを設計するには、ATL シンプル オブジェクト ウィザードのこのページを使用します。

ATL プロジェクトや ATL COM クラスの詳細については、次を参照してください。 [ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)します。

**スレッド モデル**  
スレッドを管理する方法を示します。 既定では、プロジェクトを使用して**アパートメント**スレッド処理します。

参照してください[プロジェクトのスレッド モデルを指定する](../../atl/specifying-the-threading-model-for-a-project-atl.md)詳細についてはします。

|オプション|説明|
|------------|-----------------|
|**Single**|オブジェクトが常にプライマリ COM スレッドで実行されることを指定します。 参照してください[シングル スレッド アパートメント](/windows/desktop/com/single-threaded-apartments)と[InprocServer32](/windows/desktop/com/inprocserver32)詳細についてはします。|
|**アパートメント**|アパートメント スレッド オブジェクトを使用するを指定します。 1 つのと同じスレッド アパートメント。 アパートメント スレッド コンポーネントの各オブジェクトには、オブジェクトの有効期間中、そのスレッドのアパートメントが割り当てられています。ただし、複数のスレッドは、複数のオブジェクトで使用できます。 各アパートメントでは、特定のスレッドに関連付けられているしが Windows メッセージ ポンプ (既定値)。<br /><br /> 参照してください[シングル スレッド アパートメント](/windows/desktop/com/single-threaded-apartments)詳細についてはします。|
|**両方とも**|あるオブジェクトで使用できるアパートメントまたはフリー スレッドのいずれかから、作成スレッドの種類に応じてを指定します。|
|**無料**|フリー スレッド オブジェクトを使用するを指定します。 フリー スレッドは、マルチ スレッド アパートメント モデルと同じです。 参照してください[マルチ スレッド アパートメント](/windows/desktop/com/multithreaded-apartments)詳細についてはします。|
|**Neutral**|どの種類のスレッドで実行できる、オブジェクト、マルチ スレッド アパートメントのガイドラインに従うことを指定します。|

**集計**  
オブジェクトが使用するかどうかを示す[集計](/windows/desktop/com/aggregation)します。 集約オブジェクトは、クライアントに公開するインターフェイスを選択し、集約オブジェクトには、それらが実装されているかのように、インターフェイスを公開します。 集約オブジェクトのクライアントは、集約オブジェクトとのみ通信します。

|オプション|説明|
|------------|-----------------|
|はい|オブジェクトを集計できることを指定します。 これが既定値です。|
|いいえ|オブジェクトが集計されないことを指定します。|
|のみ|オブジェクトを集計する必要がありますを指定します。|

**Interface**  
オブジェクトがサポートするインターフェイスの種類を示します。 既定では、オブジェクトは、デュアル インターフェイスをサポートします。

|オプション|説明|
|------------|-----------------|
|**デュアル**|オブジェクトがデュアル インターフェイスをサポートしていることを指定します (その vtable がカスタム インターフェイス関数と遅延バインディング`IDispatch`メソッド)。 により、両方の COM クライアントと[オートメーション コント ローラー](../../mfc/automation-clients.md)オブジェクトにアクセスします。 これが既定値です。|
|**カスタム**|オブジェクトが (その vtable がカスタム インターフェイス関数) カスタム インターフェイスをサポートするように指定します。 カスタム インターフェイスはプロセスの境界をまたいで、デュアル インターフェイスよりも高速化できます。<br /><br /> -   **互換性のある automation**カスタム インターフェイスのサポートのあるオブジェクトへのアクセスは、オートメーション コント ローラー。|

**サポート**  
オブジェクトの追加のサポートを示します。

|オプション|説明|
|------------|-----------------|
|`ISupportErrorInfo`|作成のサポート、 [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md)インターフェイスのため、オブジェクトは、クライアントにエラー情報を返すことができます。|
|**コネクション ポイント**|オブジェクトの接続ポイントからの派生オブジェクトのクラスを作成することにより[IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)します。|
|**フリー スレッド マーシャラー**|同じプロセス内のスレッド間で効率的にインターフェイス ポインターをマーシャ リングするフリー スレッド マーシャラー オブジェクトを作成します。 オブジェクトの指定に使用可能な**両方**スレッド モデルとして。|
|`IObjectWithSite` **(IE オブジェクトのサポート)**|実装[IObjectWithSiteImpl](../../atl/reference/iobjectwithsiteimpl-class.md)、コンテナー オブジェクトとそのサイト間の通信をサポートする簡単な方法を提供します。|

## <a name="see-also"></a>関連項目

[ATL シンプル オブジェクト ウィザード](../../atl/reference/atl-simple-object-wizard.md)   
[ATL シンプル オブジェクト](../../atl/reference/adding-an-atl-simple-object.md)   
[プロセス サーバーのスレッド処理の問題](/windows/desktop/com/in-process-server-threading-issues)

