---
title: スマート ポインター (Modern C) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 909ef870-904c-49b6-b8cd-e9d0b7dc9435
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d532a693414fee7845c45fd548b7513ed99b38d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="smart-pointers-modern-c"></a>スマート ポインター (Modern C++)
標準ライブラリに含まれる最新の C++ プログラミングで*スマート ポインター*メモリの解放は確実にプログラムを使用する、およびリソースのリークし例外セーフです。  
  
## <a name="uses-for-smart-pointers"></a>スマート ポインターの使用  
 スマート ポインターがで定義されている、`std`で名前空間、 [\<メモリ >](../standard-library/memory.md)ヘッダー ファイルです。 非常に重要には、 [RAII](../cpp/objects-own-resources-raii.md)または*Resource Acquisition Is Initialization*プログラミングの表現。 この表現方法の主な目的は、オブジェクトのすべてのリソースが 1 行のコードで作成されて準備が完了するように、リソースの取得がオブジェクトの初期化と同時に行われるようにすることです。 具体的には、RAII の主要な原則は、ヒープ割り当てリソース (動的に割り当てられたメモリやシステム オブジェクト ハンドルなど) の所有権を、リソースを削除または解放するコードと関連するクリーンアップ コードがデストラクターに含まれるスタック割り当てオブジェクトに付与するというものです。  
  
 ほとんどの場合、生のポインターまたはリソース ハンドルを初期化して実際のリソースをポイントするとき、ポインターをすぐにスマート ポインターに渡します。 最新の C++ では、生のポインターは、パフォーマンスが重要な意味を持ち、所有権に関する混乱が発生する可能性がない限られたスコープ、ループ、またはヘルパー関数の小さなコード ブロックでのみ使用されます。  
  
 次の例では、生のポインターの宣言とスマート ポインターの宣言を比較します。  
  
 [!code-cpp[smart_pointers_intro#1](../cpp/codesnippet/CPP/smart-pointers-modern-cpp_1.cpp)]  
  
 この例に示されているように、スマート ポインターは、スタック上で宣言し、ヒープ割り当てオブジェクトをポイントする生のポインターを使用して初期化するクラス テンプレートです。 スマート ポインターは、初期化後、生のポインターを所有します。 つまり、スマート ポインターは、生のポインターが指定するメモリの削除を担当します。 スマート ポインターのデストラクターには、削除する呼び出しが含まれています。スマート ポインターはスタック上で宣言されるため、スタックの別の場所で例外がスローされた場合でも、スマート ポインターがスコープ外に移動するとデストラクターが呼び出されます。  
  
 カプセル化されたポインターには、使い慣れたポインター演算子 `->` および `*` を使用することでアクセスします。これらの演算子には、カプセル化された生のポインターを返すためにスマート ポインター クラスがオーバーロードします。  
  
 C++ のスマート ポインターの表現方法は、C# などの言語でのオブジェクト作成に似ています。オブジェクトを作成し、システムが正しい時刻にファイルの削除を実行するようにします。 違いは、別個のガベージ コレクターがバックグラウンドで実行されないことです。メモリは、標準 C++ のスコープ規則を通じて管理されるため、ランタイム環境が高速かつ効率的になります。  
  
> [!IMPORTANT]
>  特定のパラメーター リストの割り当て規則が原因でわずかなリソース リークが発生しないように、スマート ポインターは必ずパラメーター リストではなく別個のコード行に作成してください。  
  
 例を次にどのように、`unique_ptr`ラージ オブジェクトへのポインターをカプセル化する C++ 標準ライブラリのスマート ポインター型を使用できます。  
  
 [!code-cpp[smart_pointers_intro#2](../cpp/codesnippet/CPP/smart-pointers-modern-cpp_2.cpp)]  
  
 この例は、スマート ポインターを使用するために必要な次の手順を示しています。  
  
1.  自動 (ローカル) 変数としてスマート ポインターを宣言します  (スマート ポインター自体で `new` または `malloc` 式を使用しないでください)。  
  
2.  型パラメーターで、カプセル化されたポインターの pointed-to 型を指定します。  
  
3.  生のポインターを、スマート ポインター コンストラクター内の `new` オブジェクトに渡します  (これは、一部のユーティリティ関数またはスマート ポインター コンストラクターによって行われます)。  
  
4.  オーバーロードされた `->` および `*` 演算子を使用してオブジェクトにアクセスします。  
  
5.  スマート ポインターがオブジェクトを削除するようにします。  
  
 スマート ポインターは、メモリとパフォーマンスの両方の点でできる限り効率が高くなるように設計されています。 たとえば、`unique_ptr` の唯一のデータ メンバーはカプセル化されたポインターです。 これは、`unique_ptr` がそのポインターとまったく同じサイズ (4 バイトまたは 8 バイト) であることを意味します。 スマート ポインターによってオーバーロードされた * および -> 演算子を使用することでカプセル化されたポインターにアクセスしても、生のポインターに直接アクセスするよりそれほど遅くなるわけではありません。  
  
 スマート ポインターには、"ドット" 表記を使用してアクセスできる独自のメンバー関数があります。 たとえば、一部の C++ 標準ライブラリのスマート ポインターでは、ポインターの所有権を解放するリセット メンバー関数があります。 これは、次の例に示すように、スマート ポインターがスコープ外に移動する前に、スマート ポインターが所有するメモリを解放する場合に便利です。  
  
 [!code-cpp[smart_pointers_intro#3](../cpp/codesnippet/CPP/smart-pointers-modern-cpp_3.cpp)]  
  
 スマート ポインターには、通常、生のポインターに直接アクセスする方法が用意されています。 C++ 標準ライブラリのスマート ポインターが、`get`このため、メンバー関数と`CComPtr`がパブリック`p`クラスのメンバーです。 基になるポインターへの直接アクセスを用意することにより、スマート ポインターを使用して独自のコード内のメモリを管理し、スマート ポインターをサポートしないコードに生のポインターを渡すこともできます。  
  
 [!code-cpp[smart_pointers_intro#4](../cpp/codesnippet/CPP/smart-pointers-modern-cpp_4.cpp)]  
  
## <a name="kinds-of-smart-pointers"></a>スマート ポインターの種類  
 次のセクションでは、Windows プログラミング環境で使用できるさまざまな種類のスマート ポインターの概要を示し、使用するタイミングについて説明します。  
  
 **C++ 標準ライブラリのスマート ポインター**  
 これらのスマート ポインターは、Plain Old C++ Object (POCO) にポインターをカプセル化する最初のオプションとして使用します。  
  
-   `unique_ptr`   
     基になるポインターの所有者は、厳密に 1 人許可されます。 `shared_ptr` が必要であることがわかっている場合を除き、POCO の既定のオプションとして使用します。 新しい所有者に移動できますが、コピーおよび共有することはできません。 非推奨とされた `auto_ptr` を置き換えます。 `boost::scoped_ptr` に相当します。 `unique_ptr` 小さく効率的です。サイズが 1 つのポインターと高速な挿入および C++ 標準ライブラリ コレクションから取得するために右辺値参照をサポートします。 ヘッダー ファイルは `<memory>` です。 詳細については、次を参照してください。[する方法: unique_ptr インスタンスを作成して](../cpp/how-to-create-and-use-unique-ptr-instances.md)と[unique_ptr クラス](../standard-library/unique-ptr-class.md)です。  
  
-   `shared_ptr`   
     参照カウント スマート ポインターです。 複数の所有者に 1 個の生のポインターなどを割り当てる場合に使用します。たとえば、コンテナーからポインターのコピーを返し、元のポインターを維持する場合などです。 生のポインターは、`shared_ptr` のすべての所有者がスコープ外になるか、所有権を放棄するまで削除されません。 サイズはポインター 2 個です。1 個はオブジェクト用で、もう 1 個は参照カウントを含む共有コントロール ブロック用です。 ヘッダー ファイルは `<memory>` です。 詳細については、次を参照してください。[する方法: shared_ptr インスタンスを作成して](../cpp/how-to-create-and-use-shared-ptr-instances.md)と[shared_ptr クラス](../standard-library/shared-ptr-class.md)です。  
  
-   `weak_ptr`   
    `shared_ptr` と同時に使用する特殊ケースのスマート ポインターです。 `weak_ptr` は、1 つ以上の `shared_ptr` インスタンスが所有するオブジェクトへのアクセスを提供しますが、参照カウントには参加しません。 オブジェクトを観察するが、オブジェクトを維持しておく必要はない場合に使用します。 `shared_ptr` インスタンス間の循環参照を解除するいくつかのケースで必要です。 ヘッダー ファイルは `<memory>` です。 詳細については、次を参照してください。[する方法: weak_ptr インスタンスを作成して](../cpp/how-to-create-and-use-weak-ptr-instances.md)と[weak_ptr クラス](../standard-library/weak-ptr-class.md)です。  
  
 **COM オブジェクト (従来の Windows プログラミング) 用のスマート ポインター**  
 COM オブジェクトを使用する場合、スマート ポインターの適切な型でインターフェイス ポインターをラップします。 Active Template Library (ATL) は、さまざまな目的で複数のスマート ポインターを定義します。 さらに、コンパイラが .tlb ファイルからラッパー クラスを作成するときに使用する `_com_ptr_t` スマート ポインターの型を使用することもできます。 これは、ATL ヘッダー ファイルをインクルードしたくない場合に最も適しています。  
  
 [CComPtr クラス](../atl/reference/ccomptr-class.md)  
 ATL を使用できない場合以外は、これを使用してください。 `AddRef` メソッドと `Release` メソッドを使用して、参照カウントを実行します。 詳細については、次を参照してください。[する方法: 作成と使用 CComPtr および CComQIPtr インスタンス](../cpp/how-to-create-and-use-ccomptr-and-ccomqiptr-instances.md)です。  
  
 [CComQIPtr クラス](../atl/reference/ccomqiptr-class.md)  
 `CComPtr` に似ていますが、COM オブジェクトで `QueryInterface` を呼び出すための簡単な構文も提供します。 詳細については、次を参照してください。[する方法: 作成と使用 CComPtr および CComQIPtr インスタンス](../cpp/how-to-create-and-use-ccomptr-and-ccomqiptr-instances.md)です。  
  
 [CComHeapPtr クラス](../atl/reference/ccomheapptr-class.md)  
 `CoTaskMemFree` を使用してメモリを解放するオブジェクトへのスマート ポインター。  
  
 [CComGITPtr クラス](../atl/reference/ccomgitptr-class.md)  
 グローバル インターフェイス テーブル (GIT) から取得されたインターフェイスのスマート ポインターです。  
  
 [_com_ptr_t クラス](../cpp/com-ptr-t-class.md)  
 機能の点では `CComQIPtr` に似ていますが、ATL ヘッダーには依存しません。  
  
 **POCO オブジェクト用の ATL スマート ポインター**  
 COM オブジェクト用のスマート ポインターに加えて、ATL は Plain Old C++ Object 用のスマート ポインター、およびスマート ポインター コレクションも定義します。 従来の Windows プログラミングでは、これらの型は C++ 標準ライブラリのコレクションの代わりとして役立ちますコードの移植性が必要な場合に特にや場合に、C++ 標準ライブラリと ATL のプログラミング モデルを混在させたくないです。  
  
 [CAutoPtr クラス](../atl/reference/cautoptr-class.md)  
 コピー時に所有権を移動することで一意の所有権を強制するスマート ポインターです。 非推奨とされた `std::auto_ptr` クラスに相当します。  
  
 [CHeapPtr クラス](../atl/reference/cheapptr-class.md)  
 C を使用して、割り当てられているオブジェクトのスマート ポインター [malloc](../c-runtime-library/reference/malloc.md)関数。  
  
 [CAutoVectorPtr クラス](../atl/reference/cautovectorptr-class.md)  
 `new[]` を使用して割り当てられた配列のスマート ポインターです。  
  
 [CAutoPtrArray クラス](../atl/reference/cautoptrarray-class.md)  
 `CAutoPtr` 要素の配列をカプセル化するクラスです。  
  
 [CAutoPtrList クラス](../atl/reference/cautoptrlist-class.md)  
 `CAutoPtr` ノードの一覧を操作するメソッドをカプセル化するクラスです。  
  
## <a name="see-also"></a>関連項目  
 [C++ へようこそ](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [.NET 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)   
