---
title: CObject からクラスの派生 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CObject
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 177d4160972f521eeeaee56087c29e18433be87e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440239"
---
# <a name="deriving-a-class-from-cobject"></a>CObject からのクラスの派生

この記事からクラスを派生する最小手順を説明します。 [CObject](../mfc/reference/cobject-class.md)します。 その他の`CObject`クラスの記事には、特定の活用するために必要な手順が説明されています`CObject`シリアル化と診断のデバッグ サポートなどの機能です。

ディスカッションに`CObject`、「インターフェイス ファイル」と"実装ファイル"が頻繁に使用されます。 インターフェイス ファイル (多くの場合、ヘッダー ファイルと呼ばれますか。H ファイル) には、クラス宣言とその他のクラスを使用するために必要な情報が含まれています。 実装ファイル (またはします。CPP ファイル) には、クラス定義に加え、クラス メンバー関数を実装するコードが含まれています。 たとえば、という名前のクラス`CPerson`、一般にという名前のユーザー インターフェイス ファイルを作成します。H と実装ファイルのユーザーの名前。CPP します。 ただし、アプリケーション間で共有されるしない小さなクラス、インターフェイスと 1 つの実装を結合しやすいがあります。CPP ファイルです。

クラスを派生する場合に、機能の 4 つのレベルから選択できます`CObject`:

- 基本的な機能: ランタイム クラス情報またはシリアル化のサポートが含まれていません診断メモリ管理にはします。

- 基本的な機能に加えて、ランタイム クラス情報をサポートします。

- 基本的な機能に加えて、ランタイム クラス情報と動的な作成サポートします。

- 基本機能、およびランタイム クラス情報、動的な作成、およびシリアル化のサポート。

(後で基底クラスとして使用するもの) に再利用するために設計されたクラスにはランタイム クラスのサポートとシリアル化のサポート以上を含める必要があります、今後のシリアル化の必要性が予想される場合。

宣言とから派生したクラスの実装に固有の宣言と実装のマクロを使用して機能のレベルを選択する`CObject`します。

次の表では、シリアル化および実行時の情報をサポートするために使用されるマクロの間の関係を示します。

### <a name="macros-used-for-serialization-and-run-time-information"></a>シリアル化および実行時の情報を使用するマクロ

|マクロを使用|使うため|CRuntimeClass:。<br /><br /> CreateObject|CArchive::operator >><br /><br /> CArchive::operator <<|
|----------------|-----------------------|--------------------------------------|-------------------------------------------------------|
|基本的な`CObject`機能|いいえ|×|×|
|`DECLARE_DYNAMIC`|はい|×|×|
|`DECLARE_DYNCREATE`|[はい]|[はい]|×|
|`DECLARE_SERIAL`|[はい]|[はい]|はい|

#### <a name="to-use-basic-cobject-functionality"></a>CObject の基本的な機能を使用するには

1. クラスを派生する標準の C++ 構文を使用して`CObject`(またはから派生したクラスから`CObject`)。

     次の例は、派生クラスからの最も簡単なケース`CObject`:

     [!code-cpp[NVC_MFCCObjectSample#1](../mfc/codesnippet/cpp/deriving-a-class-from-cobject_1.h)]

通常、ただし、場合の一部をオーバーライドする`CObject`の新しいクラスの詳細を処理するメンバー関数。 オーバーライドする可能性があります通常など、`Dump`関数の`CObject`クラスの内容をデバッグ出力を提供します。 オーバーライドする方法の詳細について`Dump`、記事をご覧ください[診断: オブジェクトの内容をダンプ](/previous-versions/visualstudio/visual-studio-2010/sc15kz85\(v=vs.100\))します。 オーバーライドすることも、`AssertValid`関数の`CObject`クラス オブジェクトのデータ メンバーの一貫性を検証するカスタマイズされたテストを提供します。 オーバーライドする方法の説明の`AssertValid`を参照してください[MFC ASSERT_VALID と cobject::assertvalid](/previous-versions/visualstudio/visual-studio-2010/38z04tfa\(v=vs.100\))します。

この記事[機能のレベルを指定する](../mfc/specifying-levels-of-functionality.md)ランタイム クラス情報、動的オブジェクトの作成、およびシリアル化など、機能の他のレベルを指定する方法について説明します。

## <a name="see-also"></a>関連項目

[CObject の使い方](../mfc/using-cobject.md)

