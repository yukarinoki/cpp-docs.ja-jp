---
title: 'シリアル化 : シリアル化可能なクラスの作成'
ms.date: 11/04/2016
helpviewer_keywords:
- serializable class [MFC]
- DECLARE_SERIAL macro [MFC]
- default constructor [MFC]
- VERSIONABLE_SCHEMA macro [MFC]
- classes [MFC], derived
- IMPLEMENT_SERIAL macro [MFC]
- no-arguments constructor [MFC]
- Serialize method, overriding
- defaults [MFC], constructor
- CObject class [MFC], deriving serializable classes
- constructors [MFC], defining with no arguments
- serialization [MFC], serializable classes
- no default constructor
ms.assetid: 59a14d32-1cc8-4275-9829-99639beee27c
ms.openlocfilehash: 9648bd4f516a5f174534336b1ca3b42bb51ca0c4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372706"
---
# <a name="serialization-making-a-serializable-class"></a>シリアル化 : シリアル化可能なクラスの作成

クラスをシリアル化可能にするには、主に 5 つの手順が必要です。 これらは以下に示し、以下のセクションで説明します。

1. [クラスを CObject から派生](#_core_deriving_your_class_from_cobject)する (または 派生`CObject`したクラスから) 。

1. [シリアル化メンバー関数をオーバーライド](#_core_overriding_the_serialize_member_function)する 。

1. クラス宣言[でDECLARE_SERIAL マクロを使用](#_core_using_the_declare_serial_macro)します。

1. [引数を受け取らないコンストラクタを定義](#_core_defining_a_constructor_with_no_arguments)する 。

1. [クラスの実装ファイルでIMPLEMENT_SERIALマクロを使用](#_core_using_the_implement_serial_macro_in_the_implementation_file)する。

[CArchive](../mfc/reference/carchive-class.md)`Serialize`の >> 演算子と << 演算子ではなく直接呼び出す場合、最後の 3 つの手順はシリアル化に必要ありません。

## <a name="deriving-your-class-from-cobject"></a><a name="_core_deriving_your_class_from_cobject"></a>クラスを CObject から派生する

基本的なシリアル化プロトコルと機能は`CObject`、クラスで定義されます。 クラス`CObject``CPerson`を派生させることで 、 または 派生クラス`CObject``CObject`から派生します 。

## <a name="overriding-the-serialize-member-function"></a><a name="_core_overriding_the_serialize_member_function"></a>シリアル化メンバー関数のオーバーライド

クラスで定義されるメンバー関数は`Serialize`、オブジェクトの現在の状態をキャプチャするために必要なデータを実際にシリアル化します。 `CObject` この`Serialize`関数には、`CArchive`オブジェクト データの読み取りと書き込みに使用する引数があります。 [CArchive](../mfc/reference/carchive-class.md)オブジェクトには、`IsStoring`格納 (データの書き`Serialize`込み) または読み込み (データの読み取り) を示すメンバー関数があります。 その結果をガイド`IsStoring`として使用して、挿入演算子 ( ) を使用して`CArchive`オブジェクトにオブジェクトのデータを**<** 挿入するか、抽出演算子 ( )**>>** を使用してデータを抽出します。

型`CString`と**WORD**の`CObject`2 つの新しいメンバー変数から派生し、新しいメンバー変数を持つクラスを考えてみましょう。 次のクラス宣言のフラグメントは、新しいメンバー変数とオーバーライドされた`Serialize`メンバー関数の宣言を示しています。

[!code-cpp[NVC_MFCSerialization#1](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_1.h)]

#### <a name="to-override-the-serialize-member-function"></a>シリアル化メンバー関数をオーバーライドするには

1. 基本クラスのバージョンを`Serialize`呼び出して、オブジェクトの継承された部分がシリアル化されていることを確認します。

1. クラスに固有のメンバー変数を挿入または抽出します。

   挿入演算子と抽出演算子は、アーカイブ クラスと対話してデータの読み取りと書き込みを行います。 次の例は、上記で`Serialize`宣言した`CPerson`クラスを実装する方法を示しています。

   [!code-cpp[NVC_MFCSerialization#2](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_2.cpp)]

[CArchive::Read](../mfc/reference/carchive-class.md#read)および[CArchive::Write](../mfc/reference/carchive-class.md#write)メンバー関数を使用して、型指定されていない大量のデータを読み書きすることもできます。

## <a name="using-the-declare_serial-macro"></a><a name="_core_using_the_declare_serial_macro"></a>DECLARE_SERIAL マクロの使用

DECLARE_SERIAL マクロは、次に示すように、シリアル化をサポートするクラスの宣言で必要です。

[!code-cpp[NVC_MFCSerialization#3](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_3.h)]

## <a name="defining-a-constructor-with-no-arguments"></a><a name="_core_defining_a_constructor_with_no_arguments"></a>引数を指定しないコンストラクターの定義

MFC では、オブジェクトが逆シリアル化 (ディスクから読み込まれる) に応じてオブジェクトを再作成するときに、既定のコンストラクターが必要になります。 逆シリアル化プロセスでは、オブジェクトの再作成に必要な値をすべてのメンバー変数に入力します。

このコンストラクターは、パブリック、プロテクト、またはプライベートとして宣言できます。 保護またはプライベートにする場合は、シリアル化関数でのみ使用されるようにします。 コンストラクタは、必要に応じてオブジェクトを削除できる状態にする必要があります。

> [!NOTE]
> DECLARE_SERIALとIMPLEMENT_SERIALのマクロを使用するクラスで引数を持たないコンストラクタを定義し忘れると、IMPLEMENT_SERIAL マクロが使用される行に「既定のコンストラクタがありません」というコンパイラ警告が表示されます。

## <a name="using-the-implement_serial-macro-in-the-implementation-file"></a><a name="_core_using_the_implement_serial_macro_in_the_implementation_file"></a>実装ファイルでのIMPLEMENT_SERIALマクロの使用

IMPLEMENT_SERIAL マクロは、 から`CObject`シリアル化可能なクラスを派生するときに必要なさまざまな関数を定義するために使用されます。 このマクロは、実装ファイル (.CPP) あなたのクラスのために。 マクロの最初の 2 つの引数は、クラスの名前とその直下の基本クラスの名前です。

このマクロの 3 番目の引数はスキーマ番号です。 スキーマ番号は、基本的にクラスのオブジェクトのバージョン番号です。 スキーマ番号には 0 以上の整数を使用します。 (このスキーマ番号をデータベース用語と混同しないでください。

MFC シリアル化コードは、オブジェクトをメモリに読み込むときにスキーマ番号をチェックします。 ディスク上のオブジェクトのスキーマ番号がメモリ内のクラスのスキーマ番号と一致しない場合、ライブラリは`CArchiveException`、 をスローします。

`Serialize`複数のバージョン (アプリケーションの異なるバージョンで書き込まれたファイル) をメンバ関数が読み取ることができるようにするには、IMPLEMENT_SERIAL マクロの引数として*VERSIONABLE_SCHEMA*値を使用します。 使用方法と例については、クラス`GetObjectSchema``CArchive`のメンバー関数を参照してください。

から派生したクラス`CPerson`、 に対して IMPLEMENT_SERIALを使用する方法を`CObject`次の例に示します。

[!code-cpp[NVC_MFCSerialization#4](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_4.cpp)]

シリアル化可能なクラスを作成したら、「シリアル化: オブジェクトのシリアル化」で説明したように、クラス[のオブジェクトをシリアル化](../mfc/serialization-serializing-an-object.md)できます。

## <a name="see-also"></a>関連項目

[シリアル化](../mfc/serialization-in-mfc.md)
