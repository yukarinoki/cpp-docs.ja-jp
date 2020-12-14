---
description: 詳細については、「機能のレベルの指定」を参照してください。
title: 継承機能のレベルの指定
ms.date: 11/06/2018
helpviewer_keywords:
- CObject class [MFC], adding functionality to derived classes
- runtime [MFC], class information
- serialization [MFC], Cobject
- dynamic creation support
- levels [MFC], functionality in CObject
- run-time class [MFC], information support
- levels [MFC]
ms.assetid: 562669ba-c858-4f66-b5f1-b3beeea4f486
ms.openlocfilehash: 1b016cd5a41d3e09790f678a2d49d88df33d9782
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216848"
---
# <a name="specifying-levels-of-functionality"></a>継承機能のレベルの指定

この記事では、 [CObject](../mfc/reference/cobject-class.md)の派生クラスに次のレベルの機能を追加する方法について説明します。

- ランタイムクラス情報

- 動的作成のサポート

- シリアル化のサポート

機能の一般的な説明については、 `CObject` 「 [CObject からクラスを派生](../mfc/deriving-a-class-from-cobject.md)させる」を参照してください。

## <a name="to-add-run-time-class-information"></a>ランタイムクラス情報を追加するには

1. 「 `CObject` [CObject からのクラスの派生](../mfc/deriving-a-class-from-cobject.md) 」で説明されているように、からクラスを派生させます。

1. 次に示すように、クラス宣言で DECLARE_DYNAMIC マクロを使用します。

   [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/specifying-levels-of-functionality_1.h)]

1. 実装ファイル () で IMPLEMENT_DYNAMIC マクロを使用します。CPP) を使用します。 このマクロは、次のように、クラスとその基本クラスの名前を引数として受け取ります。

   [!code-cpp[NVC_MFCCObjectSample#3](../mfc/codesnippet/cpp/specifying-levels-of-functionality_2.cpp)]

> [!NOTE]
> 常に実装ファイル () に IMPLEMENT_DYNAMIC を配置します。CPP) を使用します。 IMPLEMENT_DYNAMIC マクロは、コンパイル中に1回だけ評価される必要があるため、インターフェイスファイル () では使用できません。H) が複数のファイルに含まれる可能性があります。

## <a name="to-add-dynamic-creation-support"></a>動的作成サポートを追加するには

1. からクラスを派生させ `CObject` ます。

1. クラス宣言で DECLARE_DYNCREATE マクロを使用します。

1. 引数を指定せずにコンストラクターを定義します (既定のコンストラクター)。

1. クラス実装ファイルの IMPLEMENT_DYNCREATE マクロを使用します。

## <a name="to-add-serialization-support"></a>シリアル化のサポートを追加するには

1. からクラスを派生させ `CObject` ます。

1. `Serialize`メンバー関数をオーバーライドします。

   > [!NOTE]
   > を直接呼び出す場合 `Serialize` 、つまり、ポリモーフィックなポインターを介してオブジェクトをシリアル化しない場合は、手順 3. ~ 5. を省略します。

1. クラス宣言で DECLARE_SERIAL マクロを使用します。

1. 引数を指定せずにコンストラクターを定義します (既定のコンストラクター)。

1. クラス実装ファイルの IMPLEMENT_SERIAL マクロを使用します。

> [!NOTE]
> "ポリモーフィックポインター" は、クラスのオブジェクト (を呼び出す)、またはから派生した任意のクラスのオブジェクト (B など) を指します。 ポリモーフィックなポインターを使用してシリアル化するには、フレームワークがシリアル化しているオブジェクトのランタイムクラス (B) を特定する必要があります。これは、何らかの基底クラス (A) から派生したクラスのオブジェクトである可能性があるためです。

からクラスを派生させるときにシリアル化を有効にする方法の詳細については `CObject` 、「MFC および[シリアル化](../mfc/serialization-in-mfc.md) [」](../mfc/files-in-mfc.md)の記事のファイルを参照してください。

## <a name="see-also"></a>関連項目

[CObject からのクラスの派生](../mfc/deriving-a-class-from-cobject.md)
