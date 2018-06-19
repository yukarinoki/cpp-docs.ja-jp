---
title: されます (ATL) を使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- IDispEventSimpleImpl
dev_langs:
- C++
helpviewer_keywords:
- IDispEventSimpleImpl class, using
ms.assetid: 8640ad1a-4bd0-40a5-b5e4-7322685d7aab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0cdef5012288b7f5f17040f73dfac5ec1f90d4f0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361951"
---
# <a name="using-idispeventsimpleimpl"></a>IDispEventSimpleImpl を使用します。
使用する場合`IDispEventSimpleImpl`イベントを処理する必要があります。  
  
-   クラスを派生[されます](../atl/reference/idispeventsimpleimpl-class.md)です。  
  
-   クラスには、イベント シンク マップを追加します。  
  
-   定義[_ATL_FUNC_INFO](../atl/reference/atl-func-info-structure.md)イベントを記述する構造体。  
  
-   イベント シンク マップを使用して、エントリを追加、 [SINK_ENTRY_INFO](reference/composite-control-macros.md#sink_entry_info)マクロです。  
  
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
  
 [!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventsimpleimpl_1.h)]  
  
 この例では実際に使用されるタイプ ライブラリから唯一の情報は、Word の CLSID**アプリケーション**オブジェクトとの IID、 **ApplicationEvents**インターフェイスです。 この情報は、コンパイル時にのみ使用されます。  
  
 Simple.h に次のコードが表示されます。 関連するコードにはコメントで注意します。  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#3](../atl/codesnippet/cpp/using-idispeventsimpleimpl_2.h)]  
  
 次のコードは Simple.cpp:  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#4](../atl/codesnippet/cpp/using-idispeventsimpleimpl_3.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [イベント処理](../atl/event-handling-and-atl.md)   
 [コード](../visual-cpp-samples.md)

