---
title: CObject からのクラスの派生
ms.date: 11/04/2016
helpviewer_keywords:
- DECLARE_DYNCREATE macro [MFC]
- DECLARE_SERIAL macro [MFC]
- macros [MFC], serialization
- serialization [MFC], macros
- DECLARE_DYNAMIC macro [MFC]
- derived classes [MFC], from CObject
- CObject class [MFC], deriving serializable classes
- CObject class [MFC], deriving from
ms.assetid: 5ea4ea41-08b5-4bd8-b247-c5de8c152a27
ms.openlocfilehash: 860af88512acb33ff3035b3a04609165953d80a8
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446970"
---
# <a name="deriving-a-class-from-cobject"></a>CObject からのクラスの派生

この記事では、 [CObject](../mfc/reference/cobject-class.md)からクラスを派生させるために必要な最小限の手順について説明します。 その他の `CObject` クラスの記事では、シリアル化や診断デバッグのサポートなど、特定の `CObject` 機能を利用するために必要な手順について説明します。

`CObject`のディスカッションでは、"インターフェイスファイル" と "実装ファイル" という用語が頻繁に使用されます。 インターフェイスファイル (多くの場合、ヘッダーファイルまたはと呼ばれます)。H ファイル) には、クラス宣言と、クラスを使用するために必要なその他の情報が含まれています。 実装ファイル (または。CPP ファイル) には、クラスの定義と、クラスのメンバー関数を実装するコードが含まれています。 たとえば、`CPerson`という名前のクラスでは、通常、PERSON という名前のインターフェイスファイルを作成します。H および PERSON という名前の実装ファイル.CPP. ただし、アプリケーション間で共有されない小規模なクラスでは、インターフェイスと実装を1つにまとめる方が簡単な場合があります。CPP ファイル。

`CObject`からクラスを派生するときに、4つのレベルの機能から選択できます。

- 基本機能: ランタイムクラスの情報やシリアル化はサポートされていませんが、診断メモリの管理は含まれています。

- 基本機能に加え、ランタイムクラス情報のサポート。

- 基本的な機能に加えて、ランタイムクラス情報と動的作成がサポートされています。

- 基本的な機能に加えて、ランタイムクラス情報、動的作成、およびシリアル化をサポートします。

再利用するように設計されたクラス (後で基底クラスとして機能するクラス) では、今後のシリアル化の必要性が予想される場合に、少なくともランタイムクラスのサポートとシリアル化のサポートを含める必要があります。

機能のレベルを選択するには、`CObject`から派生したクラスの宣言と実装で特定の宣言と実装マクロを使用します。

次の表に、シリアル化と実行時の情報をサポートするために使用されるマクロ間の関係を示します。

### <a name="macros-used-for-serialization-and-run-time-information"></a>シリアル化と実行時の情報に使用されるマクロ

|使用するマクロ|CObject:: IsKindOf|CRuntimeClass::<br /><br /> CreateObject|CArchive:: operator > ><br /><br /> CArchive:: operator < <|
|----------------|-----------------------|--------------------------------------|-------------------------------------------------------|
|基本的な `CObject` 機能|いいえ|いいえ|いいえ|
|`DECLARE_DYNAMIC`|はい|いいえ|いいえ|
|`DECLARE_DYNCREATE`|はい|はい|いいえ|
|`DECLARE_SERIAL`|はい|はい|はい|

#### <a name="to-use-basic-cobject-functionality"></a>CObject の基本的な機能を使用するには

1. 通常C++の構文を使用して、`CObject` (または `CObject`から派生したクラス) からクラスを派生させます。

   次の例は、`CObject`からクラスを派生させる最も単純なケースを示しています。

   [!code-cpp[NVC_MFCCObjectSample#1](../mfc/codesnippet/cpp/deriving-a-class-from-cobject_1.h)]

ただし、通常は、`CObject`の一部のメンバー関数をオーバーライドして、新しいクラスの詳細を処理することもできます。 たとえば、通常は、`CObject` の `Dump` 関数をオーバーライドして、クラスの内容のデバッグ出力を提供します。 `Dump`をオーバーライドする方法の詳細については、「[オブジェクトダンプのカスタマイズ](/previous-versions/visualstudio/visual-studio-2010/sc15kz85(v=vs.100))」を参照してください。 また、`CObject` の `AssertValid` 関数をオーバーライドして、クラスオブジェクトのデータメンバーの一貫性を検証するためのカスタマイズされたテストを行うこともできます。 `AssertValid`をオーバーライドする方法の詳細については、「 [MFC ASSERT_VALID」と「CObject:: AssertValid](reference/diagnostic-services.md#assert_valid)」を参照してください。

[機能のレベルを指定](../mfc/specifying-levels-of-functionality.md)する記事では、ランタイムクラス情報、動的オブジェクトの作成、シリアル化など、他のレベルの機能を指定する方法について説明します。

## <a name="see-also"></a>参照

[CObject の使い方](../mfc/using-cobject.md)
