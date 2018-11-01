---
title: CObject の使い方
ms.date: 11/04/2016
f1_keywords:
- CObject
helpviewer_keywords:
- examples [MFC], CObject
- root base class for MFC
- derived classes [MFC], from CObject
- MFC, base class
- CObject class [MFC]
ms.assetid: d0cd19bb-2856-4b41-abbc-620fd64cb223
ms.openlocfilehash: 443a381c33458e61ba49eb10724d31614831f422
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50564828"
---
# <a name="using-cobject"></a>CObject の使い方

[CObject](../mfc/reference/cobject-class.md)ルート基本クラスが、ほとんどの Microsoft Foundation Class ライブラリ (MFC)。 `CObject`クラスにはシリアル化のサポート、ランタイム クラス情報、オブジェクトの診断出力など、独自のプログラム オブジェクトに組み込むことが必要な多くの便利な機能が含まれています。 クラスを派生させる場合`CObject`、クラスは、これらを悪用できる`CObject`機能します。

## <a name="what-do-you-want-to-do"></a>どうしたいんですか

- [CObject からクラスを派生します。](../mfc/deriving-a-class-from-cobject.md)

- [派生クラスに、ランタイム クラス情報、動的な作成、およびシリアル化のサポートを追加します。](../mfc/specifying-levels-of-functionality.md)

- [ランタイム クラス情報へのアクセス](../mfc/accessing-run-time-class-information.md)

- [オブジェクトを動的に作成します。](../mfc/dynamic-object-creation.md)

- [診断のために、オブジェクトのデータをダンプします。](/previous-versions/visualstudio/visual-studio-2010/sc15kz85)

- オブジェクトの内部状態の検証 (を参照してください[MFC ASSERT_VALID と cobject::assertvalid](reference/diagnostic-services.md#assert_valid))

- [それ自体を永続的ストレージにシリアル化クラスします。](../mfc/serialization-in-mfc.md)

- 一覧を参照してください[CObject よくある質問。](../mfc/cobject-class-frequently-asked-questions.md)

## <a name="see-also"></a>関連項目

[概念](../mfc/mfc-concepts.md)<br/>
[MFC の一般的なトピック](../mfc/general-mfc-topics.md)<br/>
[CRuntimeClass 構造体](../mfc/reference/cruntimeclass-structure.md)<br/>
[ファイル](../mfc/files-in-mfc.md)<br/>
[シリアル化](../mfc/serialization-in-mfc.md)

