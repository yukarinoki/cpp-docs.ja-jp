---
description: 詳細については、「CObject からのクラスの派生」を参照してください。
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
ms.openlocfilehash: c6c2ea75354d783b234bc3f7cac7a08dac4f05da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240703"
---
# <a name="deriving-a-class-from-cobject"></a>CObject からのクラスの派生

この記事では、 [CObject](reference/cobject-class.md)からクラスを派生させるために必要な最小限の手順について説明します。 その他の `CObject` クラスの記事では、 `CObject` シリアル化や診断デバッグのサポートなど、特定の機能を利用するために必要な手順について説明します。

「」の説明では、 `CObject` "インターフェイスファイル" と "実装ファイル" という用語が頻繁に使用されています。 インターフェイスファイル (多くの場合、ヘッダーファイルまたはと呼ばれます)。H ファイル) には、クラス宣言と、クラスを使用するために必要なその他の情報が含まれています。 実装ファイル (または。CPP ファイル) には、クラスの定義と、クラスのメンバー関数を実装するコードが含まれています。 たとえば、という名前のクラスの場合は、 `CPerson` 通常、PERSON という名前のインターフェイスファイルを作成します。H および PERSON という名前の実装ファイル。.CPP. ただし、アプリケーション間で共有されない小規模なクラスでは、インターフェイスと実装を1つにまとめる方が簡単な場合があります。CPP ファイル。

からクラスを派生するときに、次の4つのレベルの機能から選択でき `CObject` ます。

- 基本機能: ランタイムクラスの情報やシリアル化はサポートされていませんが、診断メモリの管理は含まれています。

- 基本機能に加え、ランタイムクラス情報のサポート。

- 基本的な機能に加えて、ランタイムクラス情報と動的作成がサポートされています。

- 基本的な機能に加えて、ランタイムクラス情報、動的作成、およびシリアル化をサポートします。

再利用するように設計されたクラス (後で基底クラスとして機能するクラス) では、今後のシリアル化の必要性が予想される場合に、少なくともランタイムクラスのサポートとシリアル化のサポートを含める必要があります。

機能のレベルを選択するには、派生元のクラスの宣言と実装で特定の宣言および実装マクロを使用し `CObject` ます。

次の表に、シリアル化と実行時の情報をサポートするために使用されるマクロ間の関係を示します。

### <a name="macros-used-for-serialization-and-run-time-information"></a>シリアル化と Run-Time 情報に使用するマクロ

|使用するマクロ|CObject:: IsKindOf|CRuntimeClass::<br /><br /> CreateObject|CArchive:: operator>><br /><br /> CArchive:: operator<<|
|----------------|-----------------------|--------------------------------------|-------------------------------------------------------|
|基本的な `CObject` 機能|いいえ|いいえ|いいえ|
|`DECLARE_DYNAMIC`|はい|いいえ|いいえ|
|`DECLARE_DYNCREATE`|はい|はい|いいえ|
|`DECLARE_SERIAL`|はい|はい|はい|

#### <a name="to-use-basic-cobject-functionality"></a>CObject の基本的な機能を使用するには

1. `CObject`(またはから派生したクラスから) クラスを派生させるには、通常の C++ 構文を使用し `CObject` ます。

   次の例は、からクラスを派生させる最も単純なケースを示してい `CObject` ます。

   [!code-cpp[NVC_MFCCObjectSample#1](codesnippet/cpp/deriving-a-class-from-cobject_1.h)]

ただし、通常は、の一部のメンバー関数をオーバーライドし `CObject` て、新しいクラスの詳細を処理することもできます。 たとえば、通常、の関数をオーバーライドし `Dump` `CObject` て、クラスの内容のデバッグ出力を提供する場合があります。 をオーバーライドする方法の詳細につい `Dump` ては、「 [オブジェクトダンプのカスタマイズ](/previous-versions/visualstudio/visual-studio-2010/sc15kz85(v=vs.100))」を参照してください。 また、の関数をオーバーライドして、 `AssertValid` `CObject` クラスオブジェクトのデータメンバーの一貫性を検証するためのカスタマイズされたテストを行うこともできます。 オーバーライドする方法の詳細につい `AssertValid` ては、「 [MFC ASSERT_VALID」および「CObject:: AssertValid](reference/diagnostic-services.md#assert_valid)」を参照してください。

[機能のレベルを指定](specifying-levels-of-functionality.md)する記事では、ランタイムクラス情報、動的オブジェクトの作成、シリアル化など、他のレベルの機能を指定する方法について説明します。

## <a name="see-also"></a>関連項目

[CObject の使い方](using-cobject.md)
