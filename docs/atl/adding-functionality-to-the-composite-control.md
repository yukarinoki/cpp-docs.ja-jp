---
description: 詳細については、「複合コントロールへの機能の追加」を参照してください。
title: 複合コントロールへの機能の追加
ms.date: 11/04/2016
helpviewer_keywords:
- event handlers [C++], ActiveX controls
- composite controls, handling events
- ActiveX controls [C++], events
ms.assetid: 98f85681-9564-480d-af38-03f9733fe58b
ms.openlocfilehash: 90e1f6b0adfc33817f9fa5a6de6fbdcd276241e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166123"
---
# <a name="adding-functionality-to-the-composite-control"></a>複合コントロールへの機能の追加

必要なコントロールを複合コントロールに挿入したら、次の手順では新しい機能を追加します。 この新しい機能は通常、次の2つのカテゴリに分類されるものです。

- 追加のインターフェイスをサポートし、追加の特定の機能を使用して複合コントロールの動作をカスタマイズします。

- 含まれている ActiveX コントロール (またはコントロール) からのイベントを処理します。

この記事の目的と範囲については、このセクションの残りの部分では、ActiveX コントロールからのイベントの処理のみを中心に説明します。

> [!NOTE]
> Windows コントロールからのメッセージを処理する必要がある場合、ATL でのメッセージ処理の詳細については、「 [ウィンドウの実装](../atl/implementing-a-window.md) 」を参照してください。

ActiveX コントロールをダイアログリソースに挿入したら、コントロールを右クリックし、[ **イベントハンドラーの追加**] をクリックします。 処理するイベントを選択し、[ **追加と編集**] をクリックします。 イベントハンドラーのコードは、コントロールの .h ファイルに追加されます。

複合コントロールの ActiveX コントロールの接続ポイントは、 [CComCompositeControl:: AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)の呼び出しによって自動的に接続され、切断されます。

## <a name="see-also"></a>関連項目

[複合コントロールの基本](../atl/atl-composite-control-fundamentals.md)
