---
title: '&lt;allocators&gt;'
ms.date: 11/04/2016
f1_keywords:
- <allocators>
helpviewer_keywords:
- allocators header
ms.assetid: 4393a607-4df8-4278-bbb2-c8ec52e60b83
ms.openlocfilehash: 69c086515230fd5a9aaa039ef02b7995842fa260
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87204886"
---
# <a name="ltallocatorsgt"></a>&lt;allocators&gt;

ノード ベースのコンテナーのメモリ ブロックの割り当てと解放に役立ついくつかのテンプレートを定義します。

## <a name="syntax"></a>構文

```cpp
#include <allocators>
```

> [!NOTE]
> \<allocators>は、Visual Studio 2019 バージョン16.3 以降では非推奨とされます。

## <a name="remarks"></a>解説

\<allocators>ヘッダーには、ノードベースのコンテナーのメモリ管理戦略を選択するために使用できる6つのアロケーターテンプレートが用意されています。 これらのテンプレートで使用するため、さまざまなマルチスレッド スキーム (なしを含む) に合わせてメモリ管理方法を調整するためのさまざまな同期フィルターも用意されています。 メモリ管理戦略をメモリ使用パターンや同期要件と照合することで、アプリの速度を上げたり、メモリ要件を減らしたりすることができます。

アロケーター テンプレートを、カスタマイズまたは交換可能な再利用可能なコンポーネントと共に実装することで、追加のメモリ管理方法が提供されます。

C++ 標準ライブラリのノードベースのコンテナー (std:: list、std:: set、std:: マルチセット、std:: map、std:: multimap) は、個々のノードに要素を格納します。 特定のコンテナーの種類のノードはすべて同じサイズであるため、汎用のメモリ マネージャーの柔軟性は必要ありません。 コンパイル時に各メモリ ブロックのサイズがわかっているため、メモリ マネージャーはずっとシンプルで高速なものにできます。

ノードベースではないコンテナー (C++ 標準ライブラリコンテナー std:: vector std::d の値、std:: basic_string) と共に使用すると、アロケーターテンプレートは正常に機能しますが、既定のアロケーターよりもパフォーマンスが向上するとは限りません。

アロケーターは、指定された型のオブジェクトとオブジェクトの配列に対して、ストレージの割り当てと解放を管理するオブジェクトを記述するクラステンプレートです。 アロケーターオブジェクトは、C++ 標準ライブラリの複数のコンテナークラステンプレートによって使用されます。

アロケーターは、この型のすべてのテンプレートです。

```cpp
template<class Type>
class allocator;
```

ここでテンプレート引数 `Type` は、アロケーター インスタンスによって管理されている型です。 C++ 標準ライブラリには、で定義されている既定のアロケータークラステンプレート[アロケーター](allocator-class.md)が用意されて [\<memory>](memory.md) います。 ヘッダーには \<allocators> 、次のアロケーターが用意されています。

- [allocator_newdel](allocator-newdel-class.md)

- [allocator_unbounded](allocator-unbounded-class.md)

- [allocator_fixed_size](allocator-fixed-size-class.md)

- [allocator_variable_size](allocator-variable-size-class.md)

- [allocator_suballoc](allocator-suballoc-class.md)

- [allocator_chunklist](allocator-chunklist-class.md)

次のコード例のようなコンテナーを作成する際に、アロケーターの適切なインスタンス化を 2 番目の型引数として使用します。

```cpp
#include <list>
#include <allocators>
std::list<int, stdext::allocators::allocator_chunklist<int> > _List0;
```

_List0 は、`allocator_chunklist` と既定の同期フィルターを使用してノードを割り当てます。

マクロ [ALLOCATOR_DECL](allocators-functions.md#allocator_decl) を使用して、既定以外の同期フィルターを持つアロケーター テンプレートを作成します。

```cpp
#include <list>
#include <allocators>
ALLOCATOR_DECL(CACHE_CHUNKLIST, stdext::allocators::sync_per_thread, Alloc);
std::list<int, alloc<int> > _List1;
```

_Lst1 は、`allocator_chunklist` と [sync_per_thread](sync-per-thread-class.md) 同期フィルターを使用してノードを割り当てます。

ブロック アロケーターは、キャッシュまたはフィルターです。 キャッシュは、std:: size_t 型の引数を1つ受け取るクラステンプレートです。 1 つのサイズのメモリ ブロックを割り当ておよび割り当て解除するブロック アロケーターを定義します。 演算子を使用してメモリを取得する必要 **`new`** がありますが、 **`new`** 各ブロックに対して個別の operator 呼び出しを行う必要はありません。 たとえば、より大規模なブロックからサブ割り当てしたり、割り当て解除したブロックを後続の再割り当てのためにキャッシュしたりすることができます。

テンプレートがインスタンス化されたときに使用された std:: size_t 引数の値を再バインドできないコンパイラでは、キャッシュのメンバー関数に渡される _Sz 引数の値が割り当てられ、割り当てが解除されるとは限りません。

\<allocators>には、次のキャッシュテンプレートが用意されています。

- [cache_freelist](cache-freelist-class.md)

- [cache_suballoc](cache-suballoc-class.md)

- [cache_chunklist](cache-chunklist-class.md)

フィルターは、別のブロックアロケーターを使用してメンバー関数を実装するブロックアロケーターです。このアロケーターは、テンプレート引数として渡されます。 フィルターの最も一般的な形式は同期フィルターです。これは、別のブロック アロケーターのインスタンスのメンバー関数へのアクセスを制御するために同期ポリシーを適用します。 \<allocators>には、次の同期フィルターが用意されています。

- [sync_none](sync-none-class.md)

- [sync_per_container](sync-per-container-class.md)

- [sync_per_thread](sync-per-thread-class.md)

- [sync_shared](sync-shared-class.md)

\<allocators>また、には、複数のブロックアロケーターインスタンスを保持し、コンパイル時ではなく実行時に割り当てまたは割り当て解除に使用するインスタンスを決定するフィルター [rts_alloc](rts-alloc-class.md)も用意されています。 再バインドをコンパイルできないコンパイラと一緒に使用します。

同期ポリシーは、アロケーター インスタンスが複数のスレッドからの割り当てと割り当て解除の同時要求を処理する方法を決定します。 最も単純なポリシーは、すべての要求を基になるキャッシュ オブジェクトに直接渡し、同期の管理をユーザーに任せることです。 より複雑なポリシーは、ミューテックスを使用して、基になるキャッシュ オブジェクトへのアクセスをシリアル化することができます。

コンパイラがシングル スレッド アプリケーションとマルチ スレッド アプリケーションの両方のコンパイルをサポートしている場合、シングル スレッド アプリケーションの既定の同期フィルターは `sync_none` で、それ以外の場合は `sync_shared` になります。

キャッシュテンプレートは、 `cache_freelist` 最大クラスの引数を受け取ります。これにより、フリーリストに格納される要素の最大数が決定されます。

\<allocators>次の最大クラスを提供します。

- [max_none](max-none-class.md)

- [max_unbounded](max-unbounded-class.md)

- [max_fixed_size](max-fixed-size-class.md)

- [max_variable_size](max-variable-size-class.md)

### <a name="macros"></a>マクロ

|マクロ|説明|
|-|-|
|[ALLOCATOR_DECL](allocators-functions.md#allocator_decl)|アロケータークラステンプレートを生成します。|
|[CACHE_CHUNKLIST](allocators-functions.md#cache_chunklist)|`stdext::allocators::cache_chunklist<sizeof(Type)>` を生成します。|
|[CACHE_FREELIST](allocators-functions.md#cache_freelist)|`stdext::allocators::cache_freelist<sizeof(Type), max>` を生成します。|
|[CACHE_SUBALLOC](allocators-functions.md#cache_suballoc)|`stdext::allocators::cache_suballoc<sizeof(Type)>` を生成します。|
|[SYNC_DEFAULT](allocators-functions.md#sync_default)|同期フィルターを生成します。|

### <a name="operators"></a>オペレーター

|演算子|Description|
|-|-|
|[operator! = ( \<allocators> )](allocators-operators.md#op_neq)|指定したクラスのアロケーター オブジェクト間の非等値をテストします。|
|[operator = = ( \<allocators> )](allocators-operators.md#op_eq_eq)|指定したクラスのアロケーター オブジェクト間の等値をテストします。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[allocator_base](allocator-base-class.md)|同期フィルターからユーザー定義のアロケーターを作成するために必要な、基底クラスと共通の関数を定義します。|
|[allocator_chunklist](allocator-chunklist-class.md)|[cache_chunklist](cache-chunklist-class.md) 型のキャッシュを使用して、オブジェクトに対してストレージの割り当てと解放を管理するオブジェクトを記述します。|
|[allocator_fixed_size](allocator-fixed-size-class.md)|[cache_freelist](cache-freelist-class.md) 型のキャッシュと [max_fixed_size](max-fixed-size-class.md) で管理されている長さを使用して、型 `Type` のオブジェクトに対し、ストレージの割り当てと解放を管理するオブジェクトを記述します。|
|[allocator_newdel](allocator-newdel-class.md)|**Operator delete**を使用してメモリブロックの割り当てを解除し、メモリブロックを割り当てる**新しい演算子**を使用するアロケーターを実装します。|
|[allocator_suballoc](allocator-suballoc-class.md)|[cache_suballoc](cache-suballoc-class.md) 型のキャッシュを使用して、`Type` 型のオブジェクトに対し、ストレージの割り当てと解放を管理するオブジェクトを記述します。|
|[allocator_unbounded](allocator-unbounded-class.md)|[cache_freelist](cache-freelist-class.md) 型のキャッシュと [max_unbounded](max-unbounded-class.md) で管理されている長さを使用して、型 `Type` のオブジェクトに対し、ストレージの割り当てと解放を管理するオブジェクトを記述します。|
|[allocator_variable_size](allocator-variable-size-class.md)|[cache_freelist](cache-freelist-class.md) 型のキャッシュと [max_variable_size](max-variable-size-class.md) で管理されている長さを使用して、型 `Type` のオブジェクトに対し、ストレージの割り当てと解放を管理するオブジェクトを記述します。|
|[cache_chunklist](cache-chunklist-class.md)|1 つのサイズのメモリ ブロックを割り当ておよび割り当て解除するブロック アロケーターを定義します。|
|[cache_freelist](cache-freelist-class.md)|1 つのサイズのメモリ ブロックを割り当ておよび割り当て解除するブロック アロケーターを定義します。|
|[cache_suballoc](cache-suballoc-class.md)|1 つのサイズのメモリ ブロックを割り当ておよび割り当て解除するブロック アロケーターを定義します。|
|[freelist](freelist-class.md)|メモリ ブロックのリストを管理します。|
|[max_fixed_size](max-fixed-size-class.md)|[freelist](freelist-class.md) オブジェクトを固定の最長値までに制限する最大クラス オブジェクトを記述します。|
|[max_none](max-none-class.md)|[freelist](freelist-class.md) オブジェクトを最長値ゼロまでに制限する最大クラス オブジェクトを記述します。|
|[max_unbounded](max-unbounded-class.md)|[freelist](freelist-class.md) オブジェクトの最長値を制限しない最大クラス オブジェクトを記述します。|
|[max_variable_size](max-variable-size-class.md)|割り当てたメモリ ブロックの数にほぼ比例した最長値までに [freelist](freelist-class.md) オブジェクトを制御する、最大クラス オブジェクトを記述します。|
|[rts_alloc](rts-alloc-class.md)|Rts_alloc クラステンプレートは、キャッシュインスタンスの配列を保持し、コンパイル時ではなく実行時に割り当てと割り当て解除に使用するインスタンスを決定する[フィルター](allocators-header.md)を記述します。|
|[sync_none](sync-none-class.md)|同期を提供しない同期フィルターを記述します。|
|[sync_per_container](sync-per-container-class.md)|アロケーター オブジェクトごとに個別のキャッシュ オブジェクトを提供する同期フィルターを記述します。|
|[sync_per_thread](sync-per-thread-class.md)|スレッドごとに個別のキャッシュ オブジェクトを提供する同期フィルターを記述します。|
|[sync_shared](sync-shared-class.md)|すべてのアロケーターによって共有されているキャッシュ オブジェクトへのアクセスを制御するためにミューテックスを使用する同期フィルターを表します。|

## <a name="requirements"></a>必要条件

**ヘッダー:**\<allocators>

**名前空間:** stdext

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](cpp-standard-library-header-files.md)
