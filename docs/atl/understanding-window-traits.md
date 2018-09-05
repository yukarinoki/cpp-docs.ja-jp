---
title: ATL ウィンドウの特徴 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- window traits
ms.assetid: c90cf850-9e91-49da-9cf3-ad4efb30347d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 91ea30c79712ced6c86da0b030882fe6a88359ed
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43764044"
---
# <a name="understanding-window-traits"></a>ウィンドウの特徴を理解します。

ウィンドウの特性クラスは、ATL ウィンドウ オブジェクトを作成するために使用するスタイルを標準化するための単純なメソッドを提供します。 ウィンドウの特徴は、テンプレート パラメーターとして受け入れられます[CWindowImpl](../atl/reference/cwindowimpl-class.md)と既定のクラス レベルでのウィンドウ スタイルを指定するための手段として他の ATL ウィンドウ クラス。

ウィンドウのインスタンスの作成者がへの呼び出しで明示的にスタイルを指定しない場合[作成](../atl/reference/cwindowimpl-class.md#create)、特性クラスを使用して、適切なスタイルを使用して、ウィンドウが作成されます。 でも、特定のスタイルに設定されているウィンドウ クラスのすべてのインスタンスの他のスタイルを許容しつつ、インスタンスごとの単位で設定を確保できます。

## <a name="atl-window-traits-templates"></a>ATL ウィンドウの特徴のテンプレート

ATL には、テンプレート パラメーターを使用して、コンパイル時に既定のスタイルを設定するための 2 つのウィンドウの特徴テンプレートが用意されています。

|クラス|説明|
|-----------|-----------------|
|[CWinTraits](../atl/reference/cwintraits-class.md)|既定の呼び出しでその他のスタイルが指定されていない場合にのみ使用されるウィンドウのスタイルを指定する場合に、このテンプレートを使用して`Create`します。 コンパイル時にスタイルの設定より優先の実行時に提供するスタイル。|
|[CWinTraitsOR](../atl/reference/cwintraitsor-class.md)|ウィンドウ クラスの常に設定する必要があるスタイルを指定する場合に、このクラスを使用します。 実行時に提供されているスタイルは、ビットごとの OR 演算子を使用して、コンパイル時に設定するスタイルを使用して結合されます。|

ATL には、多数の定義済みの特殊化のこれらのテンプレートだけでなく、`CWinTraits`ウィンドウ スタイルの組み合わせを一般的に使用されるテンプレート。 参照してください、 [CWinTraits](../atl/reference/cwintraits-class.md)完全な詳細についてはドキュメントを参照します。

## <a name="custom-window-traits"></a>カスタムのウィンドウの特徴

可能性は低い状況では ATL で提供されているテンプレートの 1 つは特化は不十分なため、独自の特性クラスを作成する必要があるだけ 2 つの静的関数を実装するクラスを作成する必要があります:`GetWndStyle`と`GetWndStyleEx`:

[!code-cpp[NVC_ATL_Windowing#68](../atl/codesnippet/cpp/understanding-window-traits_1.h)]

これらの各関数に渡されるスタイル値を使用して、新しいスタイルの値を生成する実行時。 静的関数に渡されるスタイル値がスタイルの引数として渡されたものする場合は、ウィンドウの特性クラスは、ATL ウィンドウ クラスのテンプレート引数として使用されている、[作成](../atl/reference/cwindowimpl-class.md#create)です。

## <a name="see-also"></a>関連項目

[ウィンドウ クラス](../atl/atl-window-classes.md)

