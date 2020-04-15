---
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
ms.openlocfilehash: 31beff30a067416f71029c18051f214c8d4429de
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329320"
---
# <a name="supporting-idispeventimpl"></a>IDispEventImpl のサポート

テンプレート クラス[IDispEventImpl](../atl/reference/idispeventimpl-class.md)を使用して、ATL クラスのコネクション ポイント シンクをサポートできます。 コネクション ポイント シンクを使用すると、クラスで外部 COM オブジェクトから発生したイベントを処理できます。 これらのコネクション ポイント シンクは、クラスによって提供されるイベント シンク マップでマップされます。

クラスのコネクション ポイント シンクを正しく実装するには、次の手順を実行する必要があります。

- 各外部オブジェクトのタイプ ライブラリをインポートする

- インターフェイスを`IDispEventImpl`宣言する

- イベント シンク マップを宣言する

- コネクション ポイントに関するアドバイスとアドバイスを解除する

コネクション ポイント シンクの実装に必要な手順はすべて、クラスのヘッダー ファイル (.h) だけを変更することによって実行されます。

## <a name="importing-the-type-libraries"></a>タイプ ライブラリのインポート

イベントを処理する外部オブジェクトごとに、タイプ ライブラリをインポートする必要があります。 この手順では、処理できるイベントを定義し、イベント シンク マップを宣言するときに使用される情報を提供します。 [#import](../preprocessor/hash-import-directive-cpp.md)ディレクティブを使用して、これを実現できます。 サポートする各`#import`ディスパッチ インターフェイスに必要なディレクティブ行を、クラスのヘッダー ファイル (.h) に追加します。

次の例では、外部 COM サーバーのタイプ ライブラリ`MSCAL.Calendar.7`をインポートします ( ):

[!code-cpp[NVC_ATL_Windowing#141](../atl/codesnippet/cpp/supporting-idispeventimpl_1.h)]

> [!NOTE]
> サポートする外部タイプ`#import`ライブラリごとに個別のステートメントが必要です。

## <a name="declaring-the-idispeventimpl-interfaces"></a>インターフェイスを宣言します。

これで、各ディスパッチ インターフェイスのタイプ ライブラリをインポートしたので、外部ディスパッチ インターフェイスごとに`IDispEventImpl`個別のインターフェイスを宣言する必要があります。 各外部オブジェクトのインターフェイス宣言を`IDispEventImpl`追加して、クラスの宣言を変更します。 パラメーターの詳細については、「 [IDisp イベントImpl](../atl/reference/idispeventimpl-class.md)」を参照してください。

次のコードは、`DCalendarEvents`クラス`CMyCompositCtrl2`によって実装される COM オブジェクトのインターフェイスに対して、2 つのコネクション ポイント シンクを宣言します。

[!code-cpp[NVC_ATL_Windowing#142](../atl/codesnippet/cpp/supporting-idispeventimpl_2.h)]

## <a name="declaring-an-event-sink-map"></a>イベント シンク マップの宣言

イベント通知が適切な関数によって処理されるようにするには、クラスが各イベントを適切なハンドラーにルーティングする必要があります。 これは、イベント シンク マップを宣言することによって実現されます。

ATL には、このマッピングを容易にするいくつかのマクロ[、BEGIN_SINK_MAP](reference/composite-control-macros.md#begin_sink_map) [、END_SINK_MAP、](reference/composite-control-macros.md#end_sink_map)[およびSINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex)が用意されています。 標準の形式は次のとおりです。

```cpp
BEGIN_SINK_MAP(comClass)
  SINK_ENTRY_EX(id, iid, dispid, func)
  . . . //additional external event entries
END_SINK_MAP()
```

次の例では、2 つのイベント ハンドラーを持つイベント シンク マップを宣言します。

[!code-cpp[NVC_ATL_Windowing#136](../atl/codesnippet/cpp/supporting-idispeventimpl_3.h)]

実装はほぼ完了です。 最後のステップは、外部インターフェイスのアドバイスとアドバイズ解除に関するものです。

## <a name="advising-and-unadvising-the-idispeventimpl-interfaces"></a>インターフェイスのアドバイスとアドバイズの解除

最後の手順は、適切な時間にすべてのコネクション ポイントに助言 (またはアアドバイスを行う) メソッドを実装することです。 このアドバイズは、外部クライアントとオブジェクト間の通信を行う前に行う必要があります。 オブジェクトが表示される前に、オブジェクトでサポートされている各外部ディスパッチ インターフェイスが出力インターフェイスに対してクエリされます。 接続が確立され、オブジェクトからのイベントを処理するために、出力インターフェイスへの参照が使用されます。 この手順は「アドバイス」と呼ばれます。

オブジェクトが外部インターフェイスで終了したら、クラスで使用されなくなったことを出力インターフェイスに通知する必要があります。 このプロセスは「非アドバイズ」と呼ばれます。

COM オブジェクトの一意性のため、このプロシージャは実装によって異なります。 これらの詳細はこのトピックの範囲を超えており、ここでは扱いません。

## <a name="see-also"></a>関連項目

[ATL COM オブジェクトの基礎](../atl/fundamentals-of-atl-com-objects.md)
