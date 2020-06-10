---
title: 永続化と初期化の最適化
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], optimizing
- performance, ActiveX controls
- optimization, ActiveX controls
- optimizing performance, ActiveX controls
ms.assetid: e821e19e-b9eb-49ab-b719-0743420ba80b
ms.openlocfilehash: 57b98f7e2e4f9e23175b8b01c2e37ff49c499949
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623994"
---
# <a name="optimizing-persistence-and-initialization"></a>永続化と初期化の最適化

既定では、コントロールの永続化と初期化は、メンバー関数によって処理され `DoPropExchange` ます。 一般的なコントロールでは、この関数には、プロパティごとに1つずつ、いくつかの**PX_** 関数 ( `PX_Color` 、など) の呼び出しが含まれてい `PX_Font` ます。

このアプローチには、1つの `DoPropExchange` 実装を初期化に使用したり、バイナリ形式で永続化したり、一部のコンテナーで使用されるいわゆる "プロパティバッグ" 形式で永続化したりするという利点があります。 この1つの関数は、プロパティとその既定値に関するすべての情報を1つの便利な場所に提供します。

ただし、この一般性には効率の低下が伴います。 **PX_** 関数は、より直接的ではありませんが、柔軟性が低く、アプローチが少ない多層実装によって、柔軟性が得られます。 さらに、コントロールが**PX_** 関数に既定値を渡す場合は、既定値が必ずしも使用されない場合でも、その既定値を毎回指定する必要があります。 既定値の生成が非常に重要なタスクである場合 (たとえば、アンビエントプロパティから値を取得した場合)、既定値が使用されていない場合に余分な不要な作業が行われます。

コントロールの関数をオーバーライドすると、コントロールのバイナリ永続化のパフォーマンスを向上させることができ `Serialize` ます。 このメンバー関数の既定の実装では、関数の呼び出しが行われ `DoPropExchange` ます。 オーバーライドすることにより、バイナリ永続化のためのより直接的な実装を提供できます。 たとえば、次の関数について考えてみ `DoPropExchange` ます。

[!code-cpp[NVC_MFC_AxOpt#1](codesnippet/cpp/optimizing-persistence-and-initialization_1.cpp)]

このコントロールのバイナリ永続化のパフォーマンスを向上させるには、次のように関数をオーバーライドし `Serialize` ます。

[!code-cpp[NVC_MFC_AxOpt#2](codesnippet/cpp/optimizing-persistence-and-initialization_2.cpp)]

`dwVersion`ローカル変数は、読み込まれているか保存されているコントロールの永続的な状態を検出するために使用できます。 [CPropExchange:: GetVersion](reference/cpropexchange-class.md#getversion)を呼び出す代わりに、この変数を使用できます。

**ブール**型プロパティの永続的な形式で小さな空白を保存するには (およびによって生成される形式との互換性を保つため `PX_Bool` )、次のようにプロパティを**バイト**として格納します。

[!code-cpp[NVC_MFC_AxOpt#3](codesnippet/cpp/optimizing-persistence-and-initialization_3.cpp)]

読み込みケースでは、一時変数が使用され、その値が割り当てられることに注意してください。これは、 *M_boolProp* **バイト**参照にキャストすることではありません。 キャストの手法によって、 *m_boolProp*の1バイトだけが変更され、残りのバイトは初期化されません。

同じコントロールに対して、次のように、 [COleControl:: OnResetState](reference/colecontrol-class.md#onresetstate)をオーバーライドすることによって、コントロールの初期化を最適化できます。

[!code-cpp[NVC_MFC_AxOpt#4](codesnippet/cpp/optimizing-persistence-and-initialization_4.cpp)]

`Serialize`と `OnResetState` はオーバーライドされましたが、関数は、 `DoPropExchange` プロパティバッグ形式で永続化に使用されているため、そのまま保持される必要があります。 これら3つの関数をすべて維持して、コンテナーが使用する永続化メカニズムに関係なく、コントロールのプロパティが一貫して管理されるようにすることが重要です。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール: 最適化](mfc-activex-controls-optimization.md)
