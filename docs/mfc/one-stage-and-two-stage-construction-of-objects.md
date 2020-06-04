---
title: 1 段階でのオブジェクトの構築と 2 段階でのオブジェクトの構築
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], creating graphic objects
- object creation [MFC], graphic objects
- objects [MFC], graphic objects
- one-stage and two-stage construction of objects [MFC]
ms.assetid: 5a1c410c-4a4b-4dd9-a2ec-ced831aa7f21
ms.openlocfilehash: 8f221ac6b63a06c65f932a695dfbf7b93ae7ac96
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375968"
---
# <a name="one-stage-and-two-stage-construction-of-objects"></a>1 段階でのオブジェクトの構築と 2 段階でのオブジェクトの構築

ペンやブラシなど、グラフィックオブジェクトを作成する方法として、次の 2 種類があります。

- *1 段階の構築*: コンストラクターを使用して、1 つのステージでオブジェクトを構築および初期化します。

- *2 段階の構築*: 2 つの別々のステージでオブジェクトを構築し、初期化します。 コンストラクターはオブジェクトを作成し、初期化関数によって初期化されます。

二段階の構造は常に安全である。 1 段階の構築では、引数が正しくない場合やメモリ割り当てが失敗した場合に、コンストラクターが例外をスローする可能性があります。 この問題は、2 段階の建設によって回避されますが、障害を確認する必要があります。 どちらの場合も、オブジェクトを破棄するプロセスは同じです。

> [!NOTE]
> これらのテクニックは、グラフィックオブジェクトだけでなく、オブジェクトの作成にも適用されます。

## <a name="example-of-both-construction-techniques"></a>両方の構築技術の例

次の簡単な例は、ペン オブジェクトを構築する両方の方法を示しています。

[!code-cpp[NVC_MFCDocViewSDI#6](../mfc/codesnippet/cpp/one-stage-and-two-stage-construction-of-objects_1.cpp)]

### <a name="what-do-you-want-to-know-more-about"></a>何についてもっと知りたいのですか?

- [グラフィックオブジェクト](../mfc/graphic-objects.md)

- [デバイス コンテキストへのグラフィック オブジェクトの選択](../mfc/selecting-a-graphic-object-into-a-device-context.md)

- [デバイス コンテキスト](../mfc/device-contexts.md)

- [ビューの描画](../mfc/drawing-in-a-view.md)

## <a name="see-also"></a>関連項目

[グラフィック オブジェクト](../mfc/graphic-objects.md)
