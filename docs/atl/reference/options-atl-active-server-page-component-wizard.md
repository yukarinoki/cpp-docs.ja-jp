---
title: オプション、ATL Active Server Page コンポーネント ウィザード |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.asp.options
dev_langs:
- C++
helpviewer_keywords:
- ATL Active Server Page Component Wizard, options
ms.assetid: 54f34e26-53c7-4456-9675-cb86e356bde0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 31549c812b4f523cb8026a0d0b15ae60e31cd1f8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364546"
---
# <a name="options-atl-active-server-page-component-wizard"></a>オプション、ATL Active Server Page コンポーネント ウィザード
効率の向上と、オブジェクトのエラーのサポートを設計するには、ATL Active Server Page コンポーネント ウィザードのこのページを使用します。  
  
 ATL プロジェクトや ATL COM クラスの詳細については、次を参照してください。 [ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)です。  
  
 **スレッド処理モデル**  
 スレッドを管理するための方法を示します。 既定では、プロジェクトを使用して**アパートメント**スレッド処理します。  
  
 参照してください[プロジェクトのスレッド モデルを指定する](../../atl/specifying-the-threading-model-for-a-project-atl.md)詳細についてはします。  
  
|オプション|説明|  
|------------|-----------------|  
|`Single`|オブジェクトが 1 つのスレッド モデルを使用するを指定します。 1 つのスレッド処理モデルでのオブジェクトは、常にプライマリ COM スレッドで実行されます。 参照してください[シングル スレッド アパートメント](http://msdn.microsoft.com/library/windows/desktop/ms680112)と[InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390)詳細についてはします。|  
|**アパートメント**|アパートメント スレッド オブジェクトで使用するを指定します。 1 つのと同じスレッドのアパートメントです。 アパートメント スレッド コンポーネントの各オブジェクトには、オブジェクトの有効期間のスレッドのアパートメントが割り当てられますただし、複数のスレッドは、複数のオブジェクトで使用できます。 各アパートメントが特定のスレッドに関連付けられている、Windows メッセージ ポンプ (既定値) です。<br /><br /> 参照してください[シングル スレッド アパートメント](http://msdn.microsoft.com/library/windows/desktop/ms680112)詳細についてはします。|  
|**両方とも**|あるオブジェクトで使用できるアパートメントかフリー スレッドでは、作成スレッドの種類に応じてを指定します。|  
|**無料**|オブジェクトが空きスレッドを使用するを指定します。 フリー スレッドは、マルチ スレッド アパートメント モデルと同じです。 参照してください[マルチ スレッド アパートメント](http://msdn.microsoft.com/library/windows/desktop/ms693421)詳細についてはします。|  
|**Neutral**|マルチ スレッド アパートメントのガイドラインに従うオブジェクトがどの種類のスレッドで実行することを指定します。|  
  
 **集計**  
 オブジェクトを使用するかどうかを示す[集計](http://msdn.microsoft.com/library/windows/desktop/ms686558)です。 集約オブジェクトは、クライアントに公開するインターフェイスを選択して、集約オブジェクトには、それらが実装されている場合に、インターフェイスが公開します。 集約オブジェクトのクライアントは、集計のオブジェクトでのみ通信します。  
  
|オプション|説明|  
|------------|-----------------|  
|**はい**|オブジェクトを集計できることを指定します。 これが既定値です。|  
|**No**|オブジェクトは集計されませんを指定します。|  
|**のみ**|オブジェクトを集計する必要がありますを指定します。|  
  
 **サポート**  
 (要素の説明を追加する)  
  
|オプション|説明|  
|------------|-----------------|  
|**ISupportErrorInfo**|サポートを作成、 [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md)インターフェイスのため、オブジェクトは、クライアントにエラー情報を返すことができます。|  
|**コネクション ポイント**|オブジェクトのクラスから派生することで、オブジェクトのコネクション ポイントを有効に[入力したコネクション](../../atl/reference/iconnectionpointcontainerimpl-class.md)です。|  
|**フリー スレッド マーシャラー**|同じプロセス内のスレッド間で効率的にインターフェイス ポインターをマーシャ リングするフリー スレッド マーシャラー オブジェクトを作成します。 いずれかを指定するオブジェクトに使用可能**両方**または**空き**スレッド モデルとします。|  
  
## <a name="see-also"></a>関連項目  
 [ATL Active Server Page コンポーネント ウィザード](../../atl/reference/atl-active-server-page-component-wizard.md)   
 [ATL Active Server Page コンポーネント](../../atl/reference/adding-an-atl-active-server-page-component.md)

