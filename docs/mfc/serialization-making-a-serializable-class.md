---
description: '詳細情報: シリアル化: シリアル化可能なクラスの作成'
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
ms.openlocfilehash: 21c45887199768094953066818acfe1b87d8d45d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217537"
---
# <a name="serialization-making-a-serializable-class"></a>シリアル化 : シリアル化可能なクラスの作成

クラスをシリアル化できるようにするには、5つの主要な手順を実行する必要があります。 これらは次のセクションで説明されています。

1. CObject (またはから派生したクラス)[からクラスを派生](#_core_deriving_your_class_from_cobject) `CObject` します。

1. [シリアル化メンバー関数をオーバーライドして](#_core_overriding_the_serialize_member_function)います。

1. クラス宣言で[DECLARE_SERIAL マクロを使用](#_core_using_the_declare_serial_macro)します。

1. [引数を受け取らないコンストラクターを定義](#_core_defining_a_constructor_with_no_arguments)します。

1. クラスの[実装ファイルで IMPLEMENT_SERIAL マクロを使用し](#_core_using_the_implement_serial_macro_in_the_implementation_file)ます。

`Serialize` [CArchive](../mfc/reference/carchive-class.md)の >> および << 演算子を使用せずに直接を呼び出した場合、最後の3つの手順はシリアル化には必要ありません。

## <a name="deriving-your-class-from-cobject"></a><a name="_core_deriving_your_class_from_cobject"></a> CObject からのクラスの派生

基本的なシリアル化プロトコルと機能は、クラスで定義されてい `CObject` ます。 `CObject`次のクラス宣言に示すように、クラスを (またはから派生したクラスから) 派生させることにより、 `CObject` `CPerson` のシリアル化プロトコルと機能にアクセスでき `CObject` ます。

## <a name="overriding-the-serialize-member-function"></a><a name="_core_overriding_the_serialize_member_function"></a> Serialize メンバー関数のオーバーライド

`Serialize`クラスで定義されているメンバー関数 `CObject` は、オブジェクトの現在の状態をキャプチャするために必要なデータを実際にシリアル化する役割を担います。 関数には、 `Serialize` `CArchive` オブジェクトデータの読み取りと書き込みに使用する引数があります。 [CArchive](../mfc/reference/carchive-class.md)オブジェクトには、 `IsStoring` `Serialize` が格納 (データの書き込み)、読み込み (データの読み取り) のいずれであるかを示すメンバー関数があります。 ガイドとしての結果を使用して `IsStoring` 、 `CArchive` 挿入演算子 () を使用してオブジェクトにオブジェクトのデータを挿入し **<\<**) or extract data with the extraction operator (**>>** ます。

から派生したクラスが `CObject` あり、型と単語の2つの新しいメンバー変数があるとし `CString` ます。  次のクラス宣言フラグメントは、新しいメンバー変数と、オーバーライドされたメンバー関数の宣言を示してい `Serialize` ます。

[!code-cpp[NVC_MFCSerialization#1](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_1.h)]

#### <a name="to-override-the-serialize-member-function"></a>Serialize メンバー関数をオーバーライドするには

1. 基底クラスのバージョンのを呼び出して、 `Serialize` オブジェクトの継承された部分がシリアル化されるようにします。

1. クラスに固有のメンバー変数を挿入または抽出します。

   挿入演算子と抽出演算子は archive クラスとやり取りして、データの読み取りと書き込みを行います。 次の例は、 `Serialize` 上で宣言したクラスにを実装する方法を示してい `CPerson` ます。

   [!code-cpp[NVC_MFCSerialization#2](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_2.cpp)]

また、 [carchive:: Read](../mfc/reference/carchive-class.md#read) および [Carchive:: Write](../mfc/reference/carchive-class.md#write) メンバー関数を使用して、大量の型指定されていないデータの読み取りと書き込みを行うこともできます。

## <a name="using-the-declare_serial-macro"></a><a name="_core_using_the_declare_serial_macro"></a> DECLARE_SERIAL マクロの使用

次に示すように、シリアル化をサポートするクラスの宣言には、DECLARE_SERIAL マクロが必要です。

[!code-cpp[NVC_MFCSerialization#3](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_3.h)]

## <a name="defining-a-constructor-with-no-arguments"></a><a name="_core_defining_a_constructor_with_no_arguments"></a> 引数を指定せずにコンストラクターを定義する

MFC では、オブジェクトが逆シリアル化されるときに (ディスクから読み込まれる)、既定のコンストラクターが必要になります。 逆シリアル化プロセスでは、オブジェクトを再作成するために必要な値がすべてのメンバー変数に入力されます。

このコンストラクターは、public、protected、または private として宣言できます。 保護またはプライベートにすると、シリアル化関数によってのみ使用されるようになります。 コンストラクターは、必要に応じてオブジェクトを削除できる状態にする必要があります。

> [!NOTE]
> DECLARE_SERIAL と IMPLEMENT_SERIAL マクロを使用するクラスに引数のないコンストラクターを定義し忘れた場合、IMPLEMENT_SERIAL マクロが使用されている行に "既定のコンストラクターは使用できません" というコンパイラの警告が表示されます。

## <a name="using-the-implement_serial-macro-in-the-implementation-file"></a><a name="_core_using_the_implement_serial_macro_in_the_implementation_file"></a> 実装ファイルでの IMPLEMENT_SERIAL マクロの使用

IMPLEMENT_SERIAL マクロは、からシリアル化可能なクラスを派生させるときに必要なさまざまな関数を定義するために使用され `CObject` ます。 このマクロは、実装ファイル () で使用します。CPP) を使用します。 マクロの最初の2つの引数は、クラスの名前と、その直接の基底クラスの名前です。

このマクロの3番目の引数は、スキーマ番号です。 スキーマ番号は、本質的にはクラスのオブジェクトのバージョン番号です。 スキーマ番号には0以上の整数を使用してください。 (このスキーマ番号はデータベース用語と混同しないでください)。

MFC シリアル化コードは、オブジェクトをメモリに読み込むときにスキーマ番号をチェックします。 ディスク上のオブジェクトのスキーマ番号がメモリ内のクラスのスキーマ番号と一致しない場合、ライブラリはをスローし `CArchiveException` 、プログラムが正しくないバージョンのオブジェクトを読み取ることを防ぎます。

`Serialize`メンバー関数が複数のバージョン (異なるバージョンのアプリケーションで記述されたファイル) を読み取ることができるようにする場合は、IMPLEMENT_SERIAL マクロの引数として *VERSIONABLE_SCHEMA* 値を使用できます。 使用方法と例については、「 `GetObjectSchema` クラスのメンバー関数」を参照してください `CArchive` 。

次の例は、から派生したクラスの IMPLEMENT_SERIAL を使用する方法を示して `CPerson` い `CObject` ます。

[!code-cpp[NVC_MFCSerialization#4](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_4.cpp)]

シリアル化可能なクラスを作成した後は、「 [シリアル化: オブジェクト](../mfc/serialization-serializing-an-object.md)のシリアル化」で説明されているように、クラスのオブジェクトをシリアル化できます。

## <a name="see-also"></a>関連項目

[シリアル化](../mfc/serialization-in-mfc.md)
