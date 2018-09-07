---
title: 複合コントロールへの機能の追加 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- event handlers [C++], ActiveX controls
- composite controls, handling events
- ActiveX controls [C++], events
ms.assetid: 98f85681-9564-480d-af38-03f9733fe58b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 59ee8047e17efdebbae6ee58ec243057a477caff
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751134"
---
# <a name="adding-functionality-to-the-composite-control"></a>複合コントロールへの機能の追加

複合コントロールに必要なコントロールを挿入した後、次の手順では、新しい機能を追加する必要があります。 この新しい機能は、通常は 2 つのカテゴリに分類されます。

- 追加のインターフェイスをサポートしていると、特定の機能による複合コントロールの動作をカスタマイズします。

- 格納されている ActiveX コントロール (またはコントロール) からのイベントを処理します。

目的とこの記事の範囲は、このセクションの残りの部分は、ActiveX コントロールからのイベントの処理についてのみ説明します。

> [!NOTE]
>  Windows のコントロールからのメッセージを処理する必要がある場合は、次を参照してください[ウィンドウの実装](../atl/implementing-a-window.md)atl で処理するメッセージの詳細については。

ダイアログ リソースの ActiveX コントロールを挿入すると、コントロールを右クリックし、をクリックして**イベント ハンドラーの追加**します。 イベントを処理し、をクリックする選択**の追加し、編集**します。 イベント ハンドラーのコードは、コントロールの .h ファイルに追加されます。

複合コントロールの ActiveX コントロールの接続ポイントが自動的に接続されているしへの呼び出しを使用して切断[CComCompositeControl::AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)します。

## <a name="see-also"></a>関連項目

[複合コントロールの基本](../atl/atl-composite-control-fundamentals.md)

