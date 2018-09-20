---
title: オブジェクトの 1 つのステージと 2 段階の構築 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- objects [MFC], creating graphic objects
- object creation [MFC], graphic objects
- objects [MFC], graphic objects
- one-stage and two-stage construction of objects [MFC]
ms.assetid: 5a1c410c-4a4b-4dd9-a2ec-ced831aa7f21
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a6454e34830591eccb2b696948d02f74ad8cebfd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426576"
---
# <a name="one-stage-and-two-stage-construction-of-objects"></a>1 段階でのオブジェクトの構築と 2 段階でのオブジェクトの構築

ペンとブラシなどのグラフィック オブジェクトを作成するための 2 つの手法のどちらかがあります。

- *1 つのステージ構築*: コンストラクトと、コンス トラクターを含むすべての 1 つのステージでオブジェクトを初期化します。

- *2 段階構築*: コンストラクトと、2 つの別個の段階でオブジェクトを初期化します。 コンス トラクターがオブジェクトを作成し、初期化関数では、それを初期化します。

2 段階で構築する方が安全です。 1 つのステージの構築が正しくない引数を指定するか、メモリの割り当てが失敗した場合、コンス トラクターは例外をスローする可能性があります。 エラーを確認する必要は、2 段階の構築によってに問題が回避されます。 いずれの場合も、同じプロセスは、オブジェクトを破棄します。

> [!NOTE]
>  これらの手法は、いないグラフィック オブジェクトだけで、あらゆるオブジェクトの作成に適用されます。

## <a name="example-of-both-construction-techniques"></a>両方の構築方法の例

次の簡単な例は、両方の pen オブジェクトを構築する方法を示しています。

[!code-cpp[NVC_MFCDocViewSDI#6](../mfc/codesnippet/cpp/one-stage-and-two-stage-construction-of-objects_1.cpp)]

### <a name="what-do-you-want-to-know-more-about"></a>方法については、するして操作を行います

- [グラフィック オブジェクト](../mfc/graphic-objects.md)

- [グラフィック オブジェクトをデバイス コンテキストに選択します。](../mfc/selecting-a-graphic-object-into-a-device-context.md)

- [デバイス コンテキスト](../mfc/device-contexts.md)

- [ビューの描画](../mfc/drawing-in-a-view.md)

## <a name="see-also"></a>関連項目

[グラフィック オブジェクト](../mfc/graphic-objects.md)

