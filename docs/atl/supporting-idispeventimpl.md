---
title: IDispEventImpl をサポートする |Microsoft ドキュメント
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
- event sink maps, declaring
- IDispEventImpl class, advising and unadvising
- SINK_ENTRY macro
- type libraries, importing
- ATL, IDispEventImpl support in COM objects
- BEGIN_SINK_MAP macro
- IDispEventImpl class, declaring
ms.assetid: b957f930-6a5b-4598-8e4d-8027759957e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 680396ae912cca5f19e87697e7de0033213cc963
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362220"
---
# <a name="supporting-idispeventimpl"></a>IDispEventImpl をサポートします。
このテンプレート クラスは[IDispEventImpl](../atl/reference/idispeventimpl-class.md) ATL クラス内での接続ポイント シンクのサポートを提供するために使用できます。 接続ポイント シンクは、外部の COM オブジェクトで発生したイベントを処理するクラスを使用します。 これらの接続ポイント シンクは、クラスによって提供される、イベント シンク マップにマップされます。  
  
 クラスのコネクション ポイント シンクを正しく実装するのには、次の手順を実行する必要があります。  
  
-   各外部オブジェクトのタイプ ライブラリをインポートします。  
  
-   宣言、`IDispEventImpl`インターフェイス  
  
-   イベント シンク マップを宣言します。  
  
-   通知の接続ポイントをアドバイズと  
  
 コネクション ポイント シンクの実装に必要な手順はすべて、のみのヘッダー ファイル (.h) クラスを変更することによって実行されます。  
  
## <a name="importing-the-type-libraries"></a>タイプ ライブラリのインポート  
 各外部のオブジェクト イベントを処理するためには、タイプ ライブラリをインポートする必要があります。 この手順では、処理できるイベントを定義し、イベント シンク マップを宣言するときに使用される情報を提供します。 [#Import](../preprocessor/hash-import-directive-cpp.md)ディレクティブは、これを実現するために使用できます。 必要な追加`#import`ディレクティブの行をクラスのヘッダー ファイル (.h) をサポートする各ディスパッチ インターフェイスです。  
  
 次の例は、外部の COM サーバーのタイプ ライブラリをインポート (`MSCAL.Calendar.7`)。  
  
 [!code-cpp[NVC_ATL_Windowing#141](../atl/codesnippet/cpp/supporting-idispeventimpl_1.h)]  
  
> [!NOTE]
>  個別のする必要があります`#import`をサポートする外部のタイプ ライブラリごとにステートメントです。  
  
## <a name="declaring-the-idispeventimpl-interfaces"></a>IDispEventImpl インターフェイスの宣言  
 別の宣言する必要がありますディスパッチ インターフェイスごとのタイプ ライブラリをインポートしたら、これで`IDispEventImpl`各外部ディスパッチ インターフェイス用のインターフェイスです。 クラスの宣言を追加することによって変更、`IDispEventImpl`インターフェイス外部オブジェクトごとに宣言します。 パラメーターの詳細については、次を参照してください。 [IDispEventImpl](../atl/reference/idispeventimpl-class.md)です。  
  
 次のコードの 2 つのコネクション ポイント シンクの宣言、`DCalendarEvents`クラスによって実装された COM オブジェクトのインターフェイス、 `CMyCompositCtrl2`:  
  
 [!code-cpp[NVC_ATL_Windowing#142](../atl/codesnippet/cpp/supporting-idispeventimpl_2.h)]  
  
## <a name="declaring-an-event-sink-map"></a>イベント シンク マップを宣言します。  
 イベント通知は、適切な関数で処理するためには、クラスは各イベントを適切なハンドラーをルーティングする必要があります。 これは、イベント シンク マップを宣言することによって実現されます。  
  
 ATL には、いくつかのマクロ[BEGIN_SINK_MAP](reference/composite-control-macros.md#begin_sink_map)、 [END_SINK_MAP](reference/composite-control-macros.md#end_sink_map)、および[SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex)、このマッピングを容易にします。 標準の形式は次のとおりです。  
  
 `BEGIN_SINK_MAP(comClass)`  
  
 `SINK_ENTRY_EX(id, iid, dispid, func)`  
  
 `. . . //additional external event entries`  
  
 `END_SINK_MAP()`  
  
 次の例では、次の 2 つのイベント ハンドラーでイベント シンク マップを宣言します。  
  
 [!code-cpp[NVC_ATL_Windowing#136](../atl/codesnippet/cpp/supporting-idispeventimpl_3.h)]  
  
 実装がほぼ完了しました。 最後の手順では、通知との外部インターフェイスのアドバイズを中止を扱います。  
  
## <a name="advising-and-unadvising-the-idispeventimpl-interfaces"></a>通知とアドバイズ IDispEventImpl インターフェイス  
 最後の手順では、正しい時刻になります (アドバイズするか、) すべてのコネクション ポイント メソッドを実装します。 外部クライアントと、オブジェクト間の通信を行う前に、この通知を行う必要があります。 オブジェクトが表示される前に、オブジェクトでサポートされている各外部ディスパッチ インターフェイスが発信インターフェイスの照会されます。 接続が確立され、発信インターフェイスへの参照はオブジェクトからイベントを処理するために使用します。 この手順は「通知」と呼ばれます  
  
 外部インターフェイスで、オブジェクトが完了したら、発信インターフェイスはクラスでは使用されなく通知する必要があります。 このプロセスを「アドバイズ」と呼びます  
  
 COM オブジェクトの一意な性質上、この手順は異なります詳細と実装間での実行にします。 これらの詳細は、このトピックの範囲を超えているし、は対応していません。  
  
## <a name="see-also"></a>関連項目  
 [ATL COM オブジェクトの基礎](../atl/fundamentals-of-atl-com-objects.md)

