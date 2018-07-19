---
title: 'シリアル化: シリアル化可能なクラスの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5b8e52750f6f4589f90048e248305b2f0f5b4855
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953075"
---
# <a name="serialization-making-a-serializable-class"></a>シリアル化 : シリアル化可能なクラスの作成
5 つの主要な手順は、クラスをシリアル化可能にする必要があります。 以下に示すされ、次のセクションで説明します。  
  
1.  [CObject からクラスを派生](#_core_deriving_your_class_from_cobject)(またはいずれかのクラスから派生したから`CObject`)。  
  
2.  [メンバー関数をオーバーライドする](#_core_overriding_the_serialize_member_function)です。  
  
3.  [DECLARE_SERIAL マクロを使用して](#_core_using_the_declare_serial_macro)クラス宣言にします。  
  
4.  [引数を受け取らないコンス トラクターを定義する](#_core_defining_a_constructor_with_no_arguments)です。  
  
5.  [IMPLEMENT_SERIAL マクロを使用して、実装ファイルに](#_core_using_the_implement_serial_macro_in_the_implementation_file)クラスです。  
  
 呼び出す場合`Serialize`直接ではなくを通じて、>> と << の演算子[CArchive](../mfc/reference/carchive-class.md)、最後の 3 つの手順はシリアル化に必要ではありません。  
  
##  <a name="_core_deriving_your_class_from_cobject"></a> CObject からクラスを派生します。  
 基本的なシリアル化と機能が定義されて、`CObject`クラスです。 クラスを派生させることにより`CObject`(またはから派生したクラスから`CObject`) クラスの次の宣言に示すように、 `CPerson`、シリアル化のプロトコルとの機能にアクセスできます。`CObject`です。  
  
##  <a name="_core_overriding_the_serialize_member_function"></a> オーバーライドする、メンバー関数をシリアル化  
 `Serialize`で定義されているメンバー関数、`CObject`クラス、オブジェクトの現在の状態をキャプチャするために必要なデータを実際にシリアル化します。 `Serialize`関数には、`CArchive`オブジェクトのデータの読み書きに使用される引数。 [CArchive](../mfc/reference/carchive-class.md)オブジェクトがメンバー関数の場合、`IsStoring`を示すかどうか`Serialize`が (データの書き込み) を格納するか、読み込み (データの読み取り)。 結果を使用して`IsStoring`をガイドとしていずれかのデータを挿入するオブジェクトので、`CArchive`挿入演算子を持つオブジェクト (**<\<**) または抽出演算子 (でデータを抽出**>>**).  
  
 派生したクラスを考えます`CObject`型の新しい 2 つのメンバー変数は、`CString`と**WORD**です。 次クラス宣言を示して、新しいメンバー変数とオーバーライドの宣言`Serialize`メンバー関数。  
  
 [!code-cpp[NVC_MFCSerialization#1](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_1.h)]  
  
#### <a name="to-override-the-serialize-member-function"></a>メンバー関数をオーバーライドするには  
  
1.  基本クラス バージョンを呼び出す`Serialize`オブジェクトの継承された部分がシリアル化されることを確認します。  
  
2.  挿入またはクラスに固有のメンバー変数を抽出します。  
  
     挿入と抽出演算子は、データを読み書きするアーカイブ クラスと対話します。 次の例は、実装する方法を示しています。`Serialize`の、`CPerson`上で宣言したクラス。  
  
     [!code-cpp[NVC_MFCSerialization#2](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_2.cpp)]  
  
 使用することも、[読み書きするとき](../mfc/reference/carchive-class.md#read)と[CArchive::Write](../mfc/reference/carchive-class.md#write)大量の型指定されていないデータを読み書きするメンバー関数。  
  
##  <a name="_core_using_the_declare_serial_macro"></a> DECLARE_SERIAL マクロを使用します。  
 次のように、シリアル化をサポートするクラスの宣言で DECLARE_SERIAL マクロが必要です。  
  
 [!code-cpp[NVC_MFCSerialization#3](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_3.h)]  
  
##  <a name="_core_defining_a_constructor_with_no_arguments"></a> 引数なしのコンス トラクターを定義します。  
 MFC では、それらが逆シリアル化 (ディスクから読み込まれる) と、オブジェクトを再作成時に既定のコンス トラクターが必要です。 逆シリアル化プロセスは、オブジェクトを再作成に必要な値を持つすべてのメンバー変数を入力します。  
  
 このコンス トラクターは、パブリック、プロテクト、またはプライベートに宣言できます。 加えた場合、プライベート、保護されたまたは、それがのみ使用されることによってシリアル化の関数を確認できます。 コンス トラクターは、必要に応じて削除することを許可する状態オブジェクトを配置する必要があります。  
  
> [!NOTE]
>  忘れた場合は、ストリームのマクロを使用するクラスに引数なしのコンス トラクターを定義する、IMPLEMENT_SERIAL マクロが使用されている行に「既定コンス トラクターがない使用可能な」コンパイラの警告が表示されます。  
  
##  <a name="_core_using_the_implement_serial_macro_in_the_implementation_file"></a> IMPLEMENT_SERIAL マクロを使用して、実装ファイル  
 IMPLEMENT_SERIAL マクロは、さまざまな関数を定義するために必要なときに、シリアル化可能なからクラスを派生するために使用`CObject`です。 実装ファイルでこのマクロを使用する (です。CPP) クラス。 マクロの最初の 2 つの引数は、クラスの名前とその直接の基本クラスの名前です。  
  
 このマクロの 3 番目の引数は、スキーマの数です。 スキーマ番号は、本質的に、クラスのオブジェクトのバージョン番号です。 スキーマの数を 0 以上の整数を使用します。 (と混同しないでデータベース用語では、このスキーマ数です。)  
  
 MFC のシリアル化コードをメモリにオブジェクトを読み取るときにスキーマの数を確認します。 ディスク上のオブジェクトのスキーマの数がメモリ内のクラスのスキーマの数が一致しない場合、ライブラリがスローされます、`CArchiveException`オブジェクトの正しくないバージョンの読み取りからプログラムを防止します。  
  
 場合は、`Serialize`メンバー関数を複数のバージョンを読み取ることができる、別のバージョンのアプリケーションで記述されたファイルは、— 値を使用することができます*VERSIONABLE_SCHEMA* IMPLEMENT_SERIAL への引数としてマクロです。 使用状況情報と例では、次を参照してください。、`GetObjectSchema`クラスのメンバー関数`CArchive`です。  
  
 次の例は、クラスは、IMPLEMENT_SERIAL を使用する方法を示しています`CPerson`、つまりから派生した`CObject`:。  
  
 [!code-cpp[NVC_MFCSerialization#4](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_4.cpp)]  
  
 シリアル化可能なクラスを作成したら、記事に説明したように、クラスのオブジェクトがシリアル化できる[シリアル化: オブジェクトのシリアル化](../mfc/serialization-serializing-an-object.md)です。  
  
## <a name="see-also"></a>関連項目  
 [シリアル化](../mfc/serialization-in-mfc.md)

