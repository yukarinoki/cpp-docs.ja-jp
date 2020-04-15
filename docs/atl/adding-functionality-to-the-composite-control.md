---
title: 複合コントロールへの機能の追加
ms.date: 11/04/2016
helpviewer_keywords:
- event handlers [C++], ActiveX controls
- composite controls, handling events
- ActiveX controls [C++], events
ms.assetid: 98f85681-9564-480d-af38-03f9733fe58b
ms.openlocfilehash: 5de18f863831973af384d2456adb5b2214f0dd68
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317421"
---
# <a name="adding-functionality-to-the-composite-control"></a>複合コントロールへの機能の追加

必要なコントロールを複合コントロールに挿入したら、次の手順では新しい機能を追加します。 この新しい機能は、通常、2 つのカテゴリに分類されます。

- 追加のインターフェイスをサポートし、追加の特定の機能を使用して複合コントロールの動作をカスタマイズします。

- 含まれている ActiveX コントロール (またはコントロール) からのイベントを処理します。

この資料の目的と説明については、このセクションの残りの部分では、ActiveX コントロールからのイベントの処理だけを中心に説明します。

> [!NOTE]
> Windows コントロールからのメッセージを処理する必要がある場合は、ATL でのメッセージ処理の詳細については[、「ウィンドウの実装](../atl/implementing-a-window.md)」を参照してください。

ダイアログ リソースに ActiveX コントロールを挿入した後、そのコントロールを右クリックし、[**イベント ハンドラの追加**] をクリックします。 処理するイベントを選択し、[**追加および編集**] をクリックします。 イベント ハンドラー コードは、コントロールの .h ファイルに追加されます。

複合コントロールの ActiveX コントロールの接続ポイントは[、CCom コンポジット コントロール::AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)への呼び出しを介して自動的に接続および切断されます。

## <a name="see-also"></a>関連項目

[複合コントロールの基本](../atl/atl-composite-control-fundamentals.md)
