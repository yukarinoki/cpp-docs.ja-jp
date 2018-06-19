---
title: オプション、ATL シンプル オブジェクト ウィザード |Microsoft ドキュメント
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
ms.openlocfilehash: ffc38f5359b68b90f91a2643e1fbaa743a94e559
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364142"
---
# <a name="options-atl-simple-object-wizard"></a>オプション、ATL シンプル オブジェクト ウィザード
ATL シンプル オブジェクト ウィザードのこのページを使用すると、効率の向上と、オブジェクトのエラーのサポートを設計できます。  
  
 ATL プロジェクトや ATL COM クラスの詳細については、次を参照してください。 [ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)です。  
  
 **スレッド処理モデル**  
 スレッドを管理するための方法を示します。 既定では、プロジェクトを使用して**アパートメント**スレッド処理します。  
  
 参照してください[プロジェクトのスレッド モデルを指定する](../../atl/specifying-the-threading-model-for-a-project-atl.md)詳細についてはします。  
  
|オプション|説明|  
|------------|-----------------|  
|`Single`|オブジェクトが常にプライマリ COM スレッドで実行されることを指定します。 参照してください[シングル スレッド アパートメント](http://msdn.microsoft.com/library/windows/desktop/ms680112)と[InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390)詳細についてはします。|  
|**アパートメント**|アパートメント スレッド オブジェクトで使用するを指定します。 1 つのと同じスレッドのアパートメントです。 アパートメント スレッド コンポーネントの各オブジェクトには、オブジェクトの有効期間のスレッドのアパートメントが割り当てられますただし、複数のスレッドは、複数のオブジェクトで使用できます。 各アパートメントが特定のスレッドに関連付けられている、Windows メッセージ ポンプ (既定値) です。<br /><br /> 参照してください[シングル スレッド アパートメント](http://msdn.microsoft.com/library/windows/desktop/ms680112)詳細についてはします。|  
|**両方とも**|あるオブジェクトで使用できるアパートメントかフリー スレッドでは、作成スレッドの種類に応じてを指定します。|  
|**無料**|オブジェクトが空きスレッドを使用するを指定します。 フリー スレッドは、マルチ スレッド アパートメント モデルと同じです。 参照してください[マルチ スレッド アパートメント](http://msdn.microsoft.com/library/windows/desktop/ms693421)詳細についてはします。|  
|**Neutral**|マルチ スレッド アパートメントのガイドラインに従うオブジェクトがどの種類のスレッドで実行することを指定します。|  
  
 **集計**  
 オブジェクトを使用するかどうかを示す[集計](http://msdn.microsoft.com/library/windows/desktop/ms686558)です。 集約オブジェクトは、クライアントに公開するインターフェイスを選択して、集約オブジェクトには、それらが実装されている場合に、インターフェイスが公開します。 集約オブジェクトのクライアントは、集計のオブジェクトでのみ通信します。  
  
|オプション|説明|  
|------------|-----------------|  
|[はい]|オブジェクトを集計できることを指定します。 これが既定値です。|  
|×|オブジェクトは集計されませんを指定します。|  
|のみ|オブジェクトを集計する必要がありますを指定します。|  
  
 **Interface**  
 オブジェクトがサポートするインターフェイスの種類を示します。 既定では、オブジェクトは、デュアル インターフェイスをサポートします。  
  
|オプション|説明|  
|------------|-----------------|  
|**デュアル**|オブジェクトが、デュアル インターフェイスをサポートするように指定します (その vtable がカスタム インターフェイス関数と遅延バインディング`IDispatch`メソッド)。 により、両方の COM クライアントと[オートメーション コント ローラー](../../mfc/automation-clients.md)オブジェクトにアクセスします。 これが既定値です。|  
|**カスタム**|オブジェクトが、カスタム インターフェイス (その vtable がカスタム インターフェイス関数) をサポートするように指定します。 カスタム インターフェイスは特にプロセス境界を越えて、デュアル インターフェイスよりも速くなります。<br /><br /> -   **オートメーション互換**カスタム インターフェイスのサポートのあるオブジェクトへのアクセスは、オートメーション コント ローラー。|  
  
 **サポート**  
 オブジェクトの追加サポートを示します。  
  
|オプション|説明|  
|------------|-----------------|  
|**ISupportErrorInfo**|サポートを作成、 [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md)インターフェイスのため、オブジェクトは、クライアントにエラー情報を返すことができます。|  
|**コネクション ポイント**|オブジェクトのクラスから派生することで、オブジェクトのコネクション ポイントを有効に[入力したコネクション](../../atl/reference/iconnectionpointcontainerimpl-class.md)です。|  
|**フリー スレッド マーシャラー**|同じプロセス内のスレッド間で効率的にインターフェイス ポインターをマーシャ リングするフリー スレッド マーシャラー オブジェクトを作成します。 オブジェクトの指定に使用できる**両方**スレッド モデルとします。|  
|**IObjectWithSite (IE オブジェクトのサポート)**|実装して[IObjectWithSiteImpl](../../atl/reference/iobjectwithsiteimpl-class.md)コンテナー内のオブジェクトとそのサイト間の通信をサポートする簡単な方法を提供します。|  
  
## <a name="see-also"></a>関連項目  
 [ATL シンプル オブジェクト ウィザード](../../atl/reference/atl-simple-object-wizard.md)   
 [ATL シンプル オブジェクト](../../atl/reference/adding-an-atl-simple-object.md)   
 [プロセス サーバーがスレッド処理の問題](http://msdn.microsoft.com/library/windows/desktop/ms687205)

