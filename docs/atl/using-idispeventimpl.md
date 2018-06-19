---
title: IDispEventImpl (ATL) を使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- IDispEventImpl
dev_langs:
- C++
helpviewer_keywords:
- IDispEventImpl class, using
ms.assetid: 82d53b61-9d0d-45c5-aff9-2fafa468a9ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 520d1129234a26ff6eb4c402154969ad7e166211
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361152"
---
# <a name="using-idispeventimpl"></a>IDispEventImpl を使用します。
使用する場合`IDispEventImpl`イベントを処理する必要があります。  
  
-   クラスを派生[IDispEventImpl](../atl/reference/idispeventimpl-class.md)です。  
  
-   クラスには、イベント シンク マップを追加します。  
  
-   イベント シンク マップを使用して、エントリを追加、 [SINK_ENTRY](reference/composite-control-macros.md#sink_entry)または[SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex)マクロです。  
  
-   興味のある処理でメソッドを実装します。  
  
-   案内し、イベント ソースをアドバイズします。  
  
## <a name="example"></a>例  
 次の例は、処理する方法を示します、 **DocumentChange**によって Word のイベントが発生した**アプリケーション**オブジェクト。 このイベントは、メソッドとしてで定義されている、 **ApplicationEvents**ディスパッチ インターフェイスです。  
  
 例は、[コード](../visual-cpp-samples.md)です。  
  
 `[`  
  
 `uuid(000209F7-0000-0000-C000-000000000046),`  
  
 `hidden`  
  
 `]`  
  
 `dispinterface ApplicationEvents {`  
  
 `properties:`  
  
 `methods:`  
  
 `[id(0x00000001), restricted, hidden]`  
  
 `void Startup();`  
  
 `[id(0x00000002)]`  
  
 `void Quit();`  
  
 `[id(0x00000003)]`  
  
 `void DocumentChange();`  
  
 `};`  
  
 この例では`#import`を Word のタイプ ライブラリから、必要なヘッダー ファイルを生成します。 Word の他のバージョンでこの例を使用する場合は、正しい mso dll ファイルを指定する必要があります。 たとえば、Office 2000 mso9.dll を提供し、OfficeXP が mso.dll を提供します。 このコードは、stdafx.h からが簡素化されます。  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventimpl_1.h)]  
  
 NotSoSimple.h に次のコードが表示されます。 関連するコードにはコメントで注意します。  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#2](../atl/codesnippet/cpp/using-idispeventimpl_2.h)]  
  
## <a name="see-also"></a>関連項目  
 [イベント処理](../atl/event-handling-and-atl.md)   
 [コード](../visual-cpp-samples.md)

