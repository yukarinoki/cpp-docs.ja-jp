---
description: 詳細については、「CObject の使用」をご覧ください。
title: CObject の使い方
ms.date: 11/04/2016
helpviewer_keywords:
- examples [MFC], CObject
- root base class for MFC
- derived classes [MFC], from CObject
- MFC, base class
- CObject class [MFC]
ms.assetid: d0cd19bb-2856-4b41-abbc-620fd64cb223
ms.openlocfilehash: 203e2a498f787f23de21db4469e5cdd7c5543761
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271643"
---
# <a name="using-cobject"></a>CObject の使い方

[CObject](../mfc/reference/cobject-class.md) は、ほとんどの MICROSOFT FOUNDATION CLASS ライブラリ (MFC) のルート基本クラスです。 クラスには `CObject` 、シリアル化のサポート、ランタイムクラス情報、オブジェクト診断出力など、独自のプログラムオブジェクトに組み込むことのできる便利な機能が多数含まれています。 クラスをから派生させた場合 `CObject` 、クラスはこれらの機能を利用でき `CObject` ます。

## <a name="what-do-you-want-to-do"></a>どうしたいんですか

- [CObject からクラスを派生させる](../mfc/deriving-a-class-from-cobject.md)

- [派生クラスにランタイムクラス情報、動的作成、およびシリアル化のサポートを追加する](../mfc/specifying-levels-of-functionality.md)

- [ランタイムクラス情報へのアクセス](../mfc/accessing-run-time-class-information.md)

- [オブジェクトを動的に作成する](../mfc/dynamic-object-creation.md)

- [診断目的でオブジェクトのデータをダンプする](/previous-versions/visualstudio/visual-studio-2010/sc15kz85(v=vs.100))

- オブジェクトの内部状態を検証し [ます (MFC ASSERT_VALID および CObject:: AssertValid を](reference/diagnostic-services.md#assert_valid)参照してください)。

- [クラスを永続ストレージにシリアル化する](../mfc/serialization-in-mfc.md)

- CObject に関して[よく寄せられる質問](../mfc/cobject-class-frequently-asked-questions.md)の一覧を表示する

## <a name="see-also"></a>関連項目

[概念](../mfc/mfc-concepts.md)<br/>
[MFC の一般的なトピック](../mfc/general-mfc-topics.md)<br/>
[CRuntimeClass 構造体](../mfc/reference/cruntimeclass-structure.md)<br/>
[[ファイル]](../mfc/files-in-mfc.md)<br/>
[シリアル化](../mfc/serialization-in-mfc.md)
