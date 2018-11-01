---
title: オプション、ATL Active Server Page コンポーネント ウィザード
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.asp.options
helpviewer_keywords:
- ATL Active Server Page Component Wizard, options
ms.assetid: 54f34e26-53c7-4456-9675-cb86e356bde0
ms.openlocfilehash: d8d8eaa6190bd04d626b9a23c9d27d1f9daeb003
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50595638"
---
# <a name="options-atl-active-server-page-component-wizard"></a>オプション、ATL Active Server Page コンポーネント ウィザード

効率の向上およびオブジェクトのエラーのサポートを設計するには、ATL Active Server Page コンポーネント ウィザードのこのページを使用します。

ATL プロジェクトや ATL COM クラスの詳細については、次を参照してください。 [ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)します。

- **スレッド モデル**

   スレッドを管理する方法を示します。 既定では、プロジェクトを使用して**アパートメント**スレッド処理します。

   参照してください[プロジェクトのスレッド モデルを指定する](../../atl/specifying-the-threading-model-for-a-project-atl.md)詳細についてはします。

   |オプション|説明|
   |------------|-----------------|
   |**Single**|オブジェクトが 1 つのスレッド処理モデルを使用するを指定します。 1 つのスレッド処理モデルのオブジェクトは、常にプライマリ COM スレッドで実行されます。 参照してください[シングル スレッド アパートメント](/windows/desktop/com/single-threaded-apartments)と[InprocServer32](/windows/desktop/com/inprocserver32)詳細についてはします。|
   |**アパートメント**|アパートメント スレッド オブジェクトを使用するを指定します。 1 つのと同じスレッド アパートメント。 アパートメント スレッド コンポーネントの各オブジェクトには、オブジェクトの有効期間中、そのスレッドのアパートメントが割り当てられています。ただし、複数のスレッドは、複数のオブジェクトで使用できます。 各アパートメントでは、特定のスレッドに関連付けられているしが Windows メッセージ ポンプ (既定値)。<br /><br /> 参照してください[シングル スレッド アパートメント](/windows/desktop/com/single-threaded-apartments)詳細についてはします。|
   |**両方とも**|あるオブジェクトで使用できるアパートメントまたはフリー スレッドのいずれかから、作成スレッドの種類に応じてを指定します。|
   |**無料**|フリー スレッド オブジェクトを使用するを指定します。 フリー スレッドは、マルチ スレッド アパートメント モデルと同じです。 参照してください[マルチ スレッド アパートメント](/windows/desktop/com/multithreaded-apartments)詳細についてはします。|
   |**Neutral**|どの種類のスレッドで実行できる、オブジェクト、マルチ スレッド アパートメントのガイドラインに従うことを指定します。|

- **集計**

   オブジェクトが使用するかどうかを示す[集計](/windows/desktop/com/aggregation)します。 集約オブジェクトは、クライアントに公開するインターフェイスを選択し、集約オブジェクトには、それらが実装されているかのように、インターフェイスを公開します。 集約オブジェクトのクライアントは、集約オブジェクトとのみ通信します。

   |オプション|説明|
   |------------|-----------------|
   |**はい**|オブジェクトを集計できることを指定します。 これが既定値です。|
   |**No**|オブジェクトが集計されないことを指定します。|
   |**のみ**|オブジェクトを集計する必要がありますを指定します。|

- **サポート**

   その他のサポート オプション:

   |オプション|説明|
   |------------|-----------------|
   |**ISupportErrorInfo**|作成のサポート、 [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md)インターフェイスのため、オブジェクトは、クライアントにエラー情報を返すことができます。|
   |**コネクション ポイント**|オブジェクトの接続ポイントからの派生オブジェクトのクラスを作成することにより[IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)します。|
   |**フリー スレッド マーシャラー**|同じプロセス内のスレッド間で効率的にインターフェイス ポインターをマーシャ リングするフリー スレッド マーシャラー オブジェクトを作成します。 いずれかを指定するオブジェクトに使用可能**両方**または**Free**スレッド モデルとして。|

## <a name="see-also"></a>関連項目

[ATL Active Server Page コンポーネント ウィザード](../../atl/reference/atl-active-server-page-component-wizard.md)<br/>
[ATL Active Server Page コンポーネント](../../atl/reference/adding-an-atl-active-server-page-component.md)

