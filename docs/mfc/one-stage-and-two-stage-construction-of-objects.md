---
description: 詳細については、オブジェクトの One-Stage と Two-Stage 構築に関するページを参照してください。
title: 1 段階でのオブジェクトの構築と 2 段階でのオブジェクトの構築
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], creating graphic objects
- object creation [MFC], graphic objects
- objects [MFC], graphic objects
- one-stage and two-stage construction of objects [MFC]
ms.assetid: 5a1c410c-4a4b-4dd9-a2ec-ced831aa7f21
ms.openlocfilehash: d46a8d380c263c4ce18671f02b11d5b058bc8410
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243914"
---
# <a name="one-stage-and-two-stage-construction-of-objects"></a>1 段階でのオブジェクトの構築と 2 段階でのオブジェクトの構築

ペンやブラシなどのグラフィックオブジェクトを作成するには、次の2つの方法があります。

- *1 段階構築*: 1 つのステージでオブジェクトを構築および初期化します。すべてコンストラクターを使用します。

- *2 段階構築*: オブジェクトを構築し、2つの異なるステージで初期化します。 コンストラクターはオブジェクトを作成し、初期化関数はオブジェクトを初期化します。

2段階の構築は常に安全です。 1段階の構築では、不適切な引数を指定した場合、またはメモリの割り当てが失敗した場合に、コンストラクターが例外をスローする可能性があります。 この問題は2段階の構築によって回避されますが、エラーをチェックする必要はあります。 どちらの場合も、オブジェクトの破棄は同じプロセスです。

> [!NOTE]
> これらの手法は、グラフィックオブジェクトだけでなく、オブジェクトの作成にも適用されます。

## <a name="example-of-both-construction-techniques"></a>両方の構築手法の例

次の簡単な例は、ペンオブジェクトを構築する両方の方法を示しています。

[!code-cpp[NVC_MFCDocViewSDI#6](codesnippet/cpp/one-stage-and-two-stage-construction-of-objects_1.cpp)]

### <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [グラフィック オブジェクト](graphic-objects.md)

- [グラフィック オブジェクトのデバイス コンテキストへの選択](selecting-a-graphic-object-into-a-device-context.md)

- [デバイス コンテキスト](device-contexts.md)

- [描画 (ビューで)](drawing-in-a-view.md)

## <a name="see-also"></a>関連項目

[グラフィックオブジェクト](graphic-objects.md)
