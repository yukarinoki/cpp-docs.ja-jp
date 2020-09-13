---
title: ATL コレクションクラスの概要
ms.date: 11/19/2018
helpviewer_keywords:
- DestructElements function
- collection classes, choosing
- ConstructElements function
- SerializeElements function
- traits classes
- collection classes, about collection classes
- CTraits classes
- collection classes
ms.assetid: 4d619d46-5b4e-41dd-b9fd-e86b1fbc00b5
ms.openlocfilehash: 039af388a3713540c6ba7d39e8b639cf83d291ff
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040861"
---
# <a name="atl-collection-classes"></a>ATL コレクション クラス

ATL には、データの格納とアクセスを行うためのクラスが多数用意されています。 どのクラスを使用するかは、次のようないくつかの要因によって異なります。

- 格納されるデータの量

- データへのアクセスの効率とパフォーマンス

- インデックスまたはキーによってデータにアクセスする権限

- データの並べ替え方法

- 個人用設定

## <a name="small-collection-classes"></a>小さいコレクションクラス

ATL には、少数のオブジェクトを処理するための次の配列クラスが用意されています。 ただし、これらのクラスは、ATL で内部的に使用できるように制限されています。 プログラムでは使用しないことをお勧めします。

|クラス|データストレージの種類|
|-----------|--------------------------|
|[CSimpleArray](../atl/reference/csimplearray-class.md)|少数のオブジェクトを処理するための配列クラスを実装します。|
|[CSimpleMap](../atl/reference/csimplemap-class.md)|少数のオブジェクトを処理するためのマッピングクラスを実装します。|

## <a name="general-purpose-collection-classes"></a>General Purpose コレクションクラス

次のクラスは、配列、リスト、およびマップを実装し、汎用コレクションクラスとして提供されます。

|クラス|データストレージの種類|
|-----------|--------------------------|
|[CAtlArray](../atl/reference/catlarray-class.md)|配列を実装します。|
|[CAtlList](../atl/reference/catllist-class.md)|リストを実装します。|
|[CAtlMap](../atl/reference/catlmap-class.md)|キーまたは値によってデータを参照できるように、マッピング構造を実装します。|
|[CRBMap](../atl/reference/crbmap-class.md)|レッドブラックアルゴリズムを使用して、マッピング構造を実装します。|
|[CRBMultiMap](../atl/reference/crbmultimap-class.md)|赤と黒の multimapping 構造体を実装します。|

これらのクラスは、デバッグビルドで使用されているときに多くのプログラミングエラーをトラップしますが、パフォーマンスを向上させるために、これらのチェックはリテールビルドでは実行されません。

## <a name="specialized-collection-classes"></a>特殊なコレクションクラス

メモリポインターとインターフェイスポインターを管理するために、さらに特殊なコレクションクラスも用意されています。

|クラス|目的|
|-----------|-------------|
|[CAutoPtrArray](../atl/reference/cautoptrarray-class.md)|スマートポインターの配列を構築するときに便利なメソッドを提供します。|
|[CAutoPtrList](../atl/reference/cautoptrlist-class.md)|スマートポインターのリストを構築するときに役立つメソッドを提供します。|
|[CComUnkArray](../atl/reference/ccomunkarray-class.md)|`IUnknown`はポインターを格納し、 [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md)テンプレートクラスのパラメーターとして使用するように設計されています。|
|[不正の Apptrlist](../atl/reference/cheapptrlist-class.md)|ヒープポインターのリストを構築するときに役立つメソッドを提供します。|
|[CInterfaceArray](../atl/reference/cinterfacearray-class.md)|COM インターフェイスポインターの配列を構築するときに役立つメソッドを提供します。|
|[CInterfaceList](../atl/reference/cinterfacelist-class.md)|COM インターフェイスポインターのリストを構築するときに役立つメソッドを提供します。|

## <a name="choosing-a-collection-class"></a>コレクションクラスの選択

次の表に示すように、使用可能な各コレクションクラスでは、さまざまなパフォーマンス特性が提供されます。

- 列2と3では、各クラスの順序付けとアクセスの特性について説明します。 表に使用されている用語 "順序付け" とは、項目を挿入または削除した順によってコレクション内の項目の位置が決まることを意味します。項目がその内容によって並べ替えられることを意味するのではありません。 用語 "インデックス付き" は、通常の配列内の項目と同様に、コレクション内の項目を整数インデックスによって取得できることを意味します。

- 列4および5には、各クラスのパフォーマンスが記述されています。 頻繁にコレクションに項目を挿入するアプリケーションでは、項目の挿入速度が特に重要です。他のアプリケーションでは、検索速度の方がより重要になる場合があります。

- 6 列目は、各形状で項目の重複が許可されるかどうかを表しています。

- 特定のコレクションクラス操作のパフォーマンスは、操作を完了するために必要な時間とコレクション内の要素の数の間の関係において表現されます。 要素の数が増えるにつれて直線的に増加する時間を取る操作は、O (n) アルゴリズムとして記述されます。 これに対し、要素の数が増えるにつれて時間がかかる操作は、O (log n) アルゴリズムとして記述されています。 そのため、パフォーマンスの点で、O (log n) アルゴリズムは、要素の数が増えるにつれて、O (n) アルゴリズムの方がはるかに多くなります。

### <a name="collection-shape-features"></a>コレクションの形状と特徴

|図形|注文済み|付ける|を挿入する<br /><br /> 要素|検索<br /><br /> 指定された要素|複製<br /><br /> 要素|
|-----------|--------------|--------------|---------------------------|--------------------------------------|-----------------------------|
|List|はい|いいえ|高速 (一定時間)|低速 O (n)|はい|
|Array|はい|Int (定数時刻)|終わりに挿入する場合を除き、O (n) を使用しない場合 (その場合は定数時間)|低速 O (n)|はい|
|マップ|No|キーで (一定時間)|高速 (一定時間)|高速 (一定時間)|いいえ (キー)、はい (値)|
|赤-黒のマップ|はい (キーによる)|キー O (log n)|高速 O (ログ n)|高速 O (ログ n)|No|
|赤-黒の Multimap|はい (キーによる)|キー O (log n) (キーごとに複数の値)|高速 O (ログ n)|高速 O (ログ n)|○ (キーごとに複数の値)|

## <a name="using-ctraits-objects"></a>CTraits オブジェクトの使用

ATL コレクションクラスは、さまざまなユーザー定義データ型を格納するために使用できるため、比較などの重要な関数をオーバーライドできるようにすると便利です。 これは、CTraits クラスを使用して実現されます。

CTraits クラスは、MFC コレクションクラスのヘルパー関数に似ていますが、より柔軟です。詳細については、「 [コレクションクラスヘルパー](../mfc/reference/collection-class-helpers.md) 」を参照してください。

コレクションクラスを構築するときに、CTraits クラスを指定するオプションがあります。 このクラスには、コレクションクラスを構成する他のメソッドによって呼び出された場合に、比較などの操作を実行するコードが含まれます。 たとえば、リストオブジェクトに独自のユーザー定義構造が含まれている場合、等価テストを再定義して、特定のメンバー変数のみを比較することができます。 このようにして、リストオブジェクトの Find メソッドは、より便利な方法で動作します。

## <a name="example"></a>例

### <a name="code"></a>コード

[!code-cpp[NVC_ATL_Utilities#112](../atl/codesnippet/cpp/atl-collection-classes_1.cpp)]

## <a name="comments"></a>コメント

CTraits クラスの一覧については、「 [コレクションクラス](../atl/collection-classes.md)」を参照してください。

次の図は、CTraits クラスのクラス階層を示しています。

![コレクション クラスの特徴階層構造](../atl/media/vctraitscollectionclasseshierarchy.gif "コレクション クラスの特徴階層構造")

## <a name="collection-classes-samples"></a>コレクションクラスのサンプル

次のサンプルは、コレクションクラスを示しています。

- [MMXSwarm サンプル](../overview/visual-cpp-samples.md)

- [DynamicConsumer サンプル](../overview/visual-cpp-samples.md)

- [UpdatePV サンプル](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)

- [Marquee サンプル](../overview/visual-cpp-samples.md)

## <a name="see-also"></a>参照

[概念](../atl/active-template-library-atl-concepts.md)<br/>
[コレクションクラス](../atl/collection-classes.md)
