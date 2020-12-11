---
description: 詳細については、IDispEventImpl のサポートに関するページをご覧ください。
title: IDispEventImpl のサポート
ms.date: 11/04/2016
helpviewer_keywords:
- event sink maps, declaring
- IDispEventImpl class, advising and unadvising
- SINK_ENTRY macro
- type libraries, importing
- ATL, IDispEventImpl support in COM objects
- BEGIN_SINK_MAP macro
- IDispEventImpl class, declaring
ms.assetid: b957f930-6a5b-4598-8e4d-8027759957e7
ms.openlocfilehash: 6a5c12e011ad0dc0f27594325a22dadddd5b92c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157374"
---
# <a name="supporting-idispeventimpl"></a>IDispEventImpl のサポート

テンプレートクラス [IDispEventImpl](../atl/reference/idispeventimpl-class.md) を使用して、ATL クラスでのコネクションポイントシンクのサポートを提供できます。 接続ポイントシンクを使用すると、クラスで外部 COM オブジェクトから発生したイベントを処理できます。 これらのコネクションポイントシンクは、クラスによって提供されるイベントシンクマップにマップされます。

クラスのコネクションポイントシンクを適切に実装するには、次の手順を完了する必要があります。

- 各外部オブジェクトのタイプライブラリをインポートする

- インターフェイスを宣言する `IDispEventImpl`

- イベントシンクマップを宣言する

- コネクションポイントのアドバイスとアドバイズ中止

コネクションポイントシンクの実装に必要な手順は、クラスのヘッダーファイル (.h) のみを変更することで実現されます。

## <a name="importing-the-type-libraries"></a>タイプライブラリのインポート

イベントを処理する外部オブジェクトごとに、タイプライブラリをインポートする必要があります。 この手順では、処理できるイベントを定義し、イベントシンクマップを宣言するときに使用される情報を提供します。 これを実現するには、 [#import](../preprocessor/hash-import-directive-cpp.md) ディレクティブを使用します。 `#import`サポートする各ディスパッチインターフェイスに必要なディレクティブラインをクラスのヘッダーファイル (.h) に追加します。

次の例では、外部 COM サーバー () のタイプライブラリをインポートし `MSCAL.Calendar.7` ます。

[!code-cpp[NVC_ATL_Windowing#141](../atl/codesnippet/cpp/supporting-idispeventimpl_1.h)]

> [!NOTE]
> `#import`サポートする外部タイプライブラリごとに個別のステートメントが必要です。

## <a name="declaring-the-idispeventimpl-interfaces"></a>IDispEventImpl インターフェイスの宣言

各ディスパッチインターフェイスのタイプライブラリをインポートしたので、外部ディスパッチインターフェイスごとに個別のインターフェイスを宣言する必要があり `IDispEventImpl` ます。 各外部オブジェクトのインターフェイス宣言を追加して、クラスの宣言を変更 `IDispEventImpl` します。 パラメーターの詳細については、「 [IDispEventImpl](../atl/reference/idispeventimpl-class.md)」を参照してください。

次のコードでは、 `DCalendarEvents` クラスによって実装される COM オブジェクトのインターフェイスに対して、2つのコネクションポイントシンクを宣言してい `CMyCompositCtrl2` ます。

[!code-cpp[NVC_ATL_Windowing#142](../atl/codesnippet/cpp/supporting-idispeventimpl_2.h)]

## <a name="declaring-an-event-sink-map"></a>イベントシンクマップの宣言

イベント通知が適切な関数によって処理されるようにするには、クラスで各イベントを適切なハンドラーにルーティングする必要があります。 これは、イベントシンクマップを宣言することで実現されます。

ATL には、 [BEGIN_SINK_MAP](reference/composite-control-macros.md#begin_sink_map)、 [END_SINK_MAP](reference/composite-control-macros.md#end_sink_map)、および [SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex)のいくつかのマクロが用意されているため、このマッピングが容易になります。 標準形式は次のとおりです。

```cpp
BEGIN_SINK_MAP(comClass)
  SINK_ENTRY_EX(id, iid, dispid, func)
  . . . //additional external event entries
END_SINK_MAP()
```

次の例では、2つのイベントハンドラーを持つイベントシンクマップを宣言します。

[!code-cpp[NVC_ATL_Windowing#136](../atl/codesnippet/cpp/supporting-idispeventimpl_3.h)]

実装はほぼ完了しています。 最後の手順は、外部インターフェイスのアドバイズと unadvising に関するものです。

## <a name="advising-and-unadvising-the-idispeventimpl-interfaces"></a>IDispEventImpl インターフェイスのアドバイズと Unadvising

最後の手順では、すべてのコネクションポイントを適切なタイミングでアドバイズ (またはアドバイズを中止) するメソッドを実装します。 このアドバイスは、外部クライアントとオブジェクト間の通信を実行する前に行う必要があります。 オブジェクトが表示される前に、オブジェクトでサポートされている各外部ディスパッチインターフェイスが、送信インターフェイスに対して照会されます。 接続が確立され、オブジェクトからのイベントを処理するために、送信インターフェイスへの参照が使用されます。 この手順を "アドバイズ" と呼びます。

オブジェクトが外部インターフェイスで終了した後、送信インターフェイスには、クラスで使用されなくなったことが通知されます。 このプロセスは "unadvising" と呼ばれます。

COM オブジェクトには固有の性質があるため、この手順の詳細と実行は実装間で異なります。 これらの詳細については、このトピックでは扱いません。

## <a name="see-also"></a>関連項目

[ATL COM オブジェクトの基礎](../atl/fundamentals-of-atl-com-objects.md)
