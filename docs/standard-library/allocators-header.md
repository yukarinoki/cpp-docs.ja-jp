---
title: '&lt;allocators&gt;'
ms.date: 11/04/2016
f1_keywords:
- <allocators>
helpviewer_keywords:
- allocators header
ms.assetid: 4393a607-4df8-4278-bbb2-c8ec52e60b83
ms.openlocfilehash: f6be154be68cd5e43fd6f934d88c04fb25be9dc5
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754446"
---
# <a name="ltallocatorsgt"></a>&lt;allocators&gt;

ノード ベースのコンテナーのメモリ ブロックの割り当てと解放に役立ついくつかのテンプレートを定義します。

## <a name="syntax"></a>構文

```cpp
#include <allocators>
```

> [!NOTE]
> \<アロケーター>は、Visual Studio 2019 バージョン 16.3 以降、非推奨です。

## <a name="remarks"></a>解説

\<allocators> ヘッダーは、ノード ベースのコンテナーのメモリ管理方法を選択するために使用できる 6 つのアロケーター テンプレートを提供します。 これらのテンプレートで使用するため、さまざまなマルチスレッド スキーム (なしを含む) に合わせてメモリ管理方法を調整するためのさまざまな同期フィルターも用意されています。 メモリ管理戦略をメモリ使用量パターンと同期要件に合わせて対応させることで、アプリの速度を上げたり、メモリ要件を削減したりできます。

アロケーター テンプレートを、カスタマイズまたは交換可能な再利用可能なコンポーネントと共に実装することで、追加のメモリ管理方法が提供されます。

C++ 標準ライブラリのノード ベースのコンテナー (std:list、std:set、std::マルチセット、std::map、および std::multimap) は、各ノードに要素を格納します。 特定のコンテナーの種類のノードはすべて同じサイズであるため、汎用のメモリ マネージャーの柔軟性は必要ありません。 コンパイル時に各メモリ ブロックのサイズがわかっているため、メモリ マネージャーはずっとシンプルで高速なものにできます。

ノード ベースでないコンテナー (C++ 標準ライブラリ コンテナー std::vector std::deque、std::basic_string など) で使用すると、アロケーター テンプレートは正しく機能しますが、既定のアロケーターよりもパフォーマンスが向上する可能性は低くなります。

アロケーターは、指定された型のオブジェクトおよびオブジェクトの配列のストレージ割り当てと解放を管理するオブジェクトを記述するクラス テンプレートです。 Alocator オブジェクトは、C++ 標準ライブラリ内のいくつかのコンテナー クラス テンプレートで使用されます。

アロケーターは、この型のすべてのテンプレートです。

```cpp
template<class Type>
class allocator;
```

ここでテンプレート引数 `Type` は、アロケーター インスタンスによって管理されている型です。 C++ 標準ライブラリには、[\<メモリ>](../standard-library/memory.md)で定義された既定のアロケーター、クラス テンプレート[アロケータ](../standard-library/allocator-class.md)が用意されています。 \<allocators> ヘッダーは、次のアロケーターを提供します。

- [allocator_newdel](../standard-library/allocator-newdel-class.md)

- [allocator_unbounded](../standard-library/allocator-unbounded-class.md)

- [allocator_fixed_size](../standard-library/allocator-fixed-size-class.md)

- [allocator_variable_size](../standard-library/allocator-variable-size-class.md)

- [allocator_suballoc](../standard-library/allocator-suballoc-class.md)

- [allocator_chunklist](../standard-library/allocator-chunklist-class.md)

次のコード例のようなコンテナーを作成する際に、アロケーターの適切なインスタンス化を 2 番目の型引数として使用します。

```cpp
#include <list>
#include <allocators>
std::list<int, stdext::allocators::allocator_chunklist<int> > _List0;
```

_List0 は、`allocator_chunklist` と既定の同期フィルターを使用してノードを割り当てます。

マクロ [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) を使用して、既定以外の同期フィルターを持つアロケーター テンプレートを作成します。

```cpp
#include <list>
#include <allocators>
ALLOCATOR_DECL(CACHE_CHUNKLIST, stdext::allocators::sync_per_thread, Alloc);
std::list<int, alloc<int> > _List1;
```

_Lst1 は、`allocator_chunklist` と [sync_per_thread](../standard-library/sync-per-thread-class.md) 同期フィルターを使用してノードを割り当てます。

ブロック アロケーターは、キャッシュまたはフィルターです。 キャッシュは、std::size_t型の引数を 1 つ受け取るクラス テンプレートです。 1 つのサイズのメモリ ブロックを割り当ておよび割り当て解除するブロック アロケーターを定義します。 演算子**new**を使用してメモリを取得する必要がありますが、ブロック**ごとに演算子**new を個別に呼び出す必要はありません。 たとえば、より大規模なブロックからサブ割り当てしたり、割り当て解除したブロックを後続の再割り当てのためにキャッシュしたりすることができます。

テンプレートのインスタンス化時に使用される std::size_t 引数の値を再バインドできないコンパイラでは、必ずしもキャッシュのメンバー関数に渡 _Szされる引数の値が割り当てと割り当て解除されるとは限りません。

\<allocators> は次のキャッシュ テンプレートを提供します。

- [cache_freelist](../standard-library/cache-freelist-class.md)

- [cache_suballoc](../standard-library/cache-suballoc-class.md)

- [cache_chunklist](../standard-library/cache-chunklist-class.md)

フィルタは、別のブロック アロケーターを使用してメンバー関数を実装するブロック アロケーターで、テンプレート引数として渡されます。 フィルターの最も一般的な形式は同期フィルターです。これは、別のブロック アロケーターのインスタンスのメンバー関数へのアクセスを制御するために同期ポリシーを適用します。 \<allocators> は次の同期フィルターを提供します。

- [sync_none](../standard-library/sync-none-class.md)

- [sync_per_container](../standard-library/sync-per-container-class.md)

- [sync_per_thread](../standard-library/sync-per-thread-class.md)

- [sync_shared](../standard-library/sync-shared-class.md)

\<allocators> は、フィルター [rts_alloc](../standard-library/rts-alloc-class.md) も提供します。これは、複数のブロック アロケーター インスタンスを保持し、コンパイル時ではなく、実行時に割り当てと割り当て解除に使用するインスタンスを判別します。 再バインドをコンパイルできないコンパイラと一緒に使用します。

同期ポリシーは、アロケーター インスタンスが複数のスレッドからの割り当てと割り当て解除の同時要求を処理する方法を決定します。 最も単純なポリシーは、すべての要求を基になるキャッシュ オブジェクトに直接渡し、同期の管理をユーザーに任せることです。 より複雑なポリシーは、ミューテックスを使用して、基になるキャッシュ オブジェクトへのアクセスをシリアル化することができます。

コンパイラがシングル スレッド アプリケーションとマルチ スレッド アプリケーションの両方のコンパイルをサポートしている場合、シングル スレッド アプリケーションの既定の同期フィルターは `sync_none` で、それ以外の場合は `sync_shared` になります。

キャッシュ テンプレート`cache_freelist`は、空きリストに格納される要素の最大数を決定する max class 引数を受け取ります。

\<allocators> は次の最大クラスを提供します。

- [max_none](../standard-library/max-none-class.md)

- [max_unbounded](../standard-library/max-unbounded-class.md)

- [max_fixed_size](../standard-library/max-fixed-size-class.md)

- [max_variable_size](../standard-library/max-variable-size-class.md)

### <a name="macros"></a>マクロ

|マクロ|説明|
|-|-|
|[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl)|アロケータ クラス テンプレートを生成します。|
|[CACHE_CHUNKLIST](../standard-library/allocators-functions.md#cache_chunklist)|`stdext::allocators::cache_chunklist<sizeof(Type)>` を生成します。|
|[CACHE_FREELIST](../standard-library/allocators-functions.md#cache_freelist)|`stdext::allocators::cache_freelist<sizeof(Type), max>` を生成します。|
|[CACHE_SUBALLOC](../standard-library/allocators-functions.md#cache_suballoc)|`stdext::allocators::cache_suballoc<sizeof(Type)>` を生成します。|
|[SYNC_DEFAULT](../standard-library/allocators-functions.md#sync_default)|同期フィルターを生成します。|

### <a name="operators"></a>オペレーター

|演算子|説明|
|-|-|
|[演算子!=\<(アロケータ>)](../standard-library/allocators-operators.md#op_neq)|指定したクラスのアロケーター オブジェクト間の非等値をテストします。|
|[operator== (\<allocators>)](../standard-library/allocators-operators.md#op_eq_eq)|指定したクラスのアロケーター オブジェクト間の等値をテストします。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[allocator_base](../standard-library/allocator-base-class.md)|同期フィルターからユーザー定義のアロケーターを作成するために必要な、基底クラスと共通の関数を定義します。|
|[allocator_chunklist](../standard-library/allocator-chunklist-class.md)|[cache_chunklist](../standard-library/cache-chunklist-class.md) 型のキャッシュを使用して、オブジェクトに対してストレージの割り当てと解放を管理するオブジェクトを記述します。|
|[allocator_fixed_size](../standard-library/allocator-fixed-size-class.md)|[cache_freelist](../standard-library/cache-freelist-class.md) 型のキャッシュと [max_fixed_size](../standard-library/max-fixed-size-class.md) で管理されている長さを使用して、型 `Type` のオブジェクトに対し、ストレージの割り当てと解放を管理するオブジェクトを記述します。|
|[allocator_newdel](../standard-library/allocator-newdel-class.md)|**演算子の削除**を使用してメモリ ブロックの割り当てを解除し、メモリ ブロックを割り当てる**新しい演算子**を使用するアロケーターを実装します。|
|[allocator_suballoc](../standard-library/allocator-suballoc-class.md)|[cache_suballoc](../standard-library/cache-suballoc-class.md) 型のキャッシュを使用して、`Type` 型のオブジェクトに対し、ストレージの割り当てと解放を管理するオブジェクトを記述します。|
|[allocator_unbounded](../standard-library/allocator-unbounded-class.md)|[cache_freelist](../standard-library/cache-freelist-class.md) 型のキャッシュと [max_unbounded](../standard-library/max-unbounded-class.md) で管理されている長さを使用して、型 `Type` のオブジェクトに対し、ストレージの割り当てと解放を管理するオブジェクトを記述します。|
|[allocator_variable_size](../standard-library/allocator-variable-size-class.md)|[cache_freelist](../standard-library/cache-freelist-class.md) 型のキャッシュと [max_variable_size](../standard-library/max-variable-size-class.md) で管理されている長さを使用して、型 `Type` のオブジェクトに対し、ストレージの割り当てと解放を管理するオブジェクトを記述します。|
|[cache_chunklist](../standard-library/cache-chunklist-class.md)|1 つのサイズのメモリ ブロックを割り当ておよび割り当て解除するブロック アロケーターを定義します。|
|[cache_freelist](../standard-library/cache-freelist-class.md)|1 つのサイズのメモリ ブロックを割り当ておよび割り当て解除するブロック アロケーターを定義します。|
|[cache_suballoc](../standard-library/cache-suballoc-class.md)|1 つのサイズのメモリ ブロックを割り当ておよび割り当て解除するブロック アロケーターを定義します。|
|[freelist](../standard-library/freelist-class.md)|メモリ ブロックのリストを管理します。|
|[max_fixed_size](../standard-library/max-fixed-size-class.md)|[freelist](../standard-library/freelist-class.md) オブジェクトを固定の最長値までに制限する最大クラス オブジェクトを記述します。|
|[max_none](../standard-library/max-none-class.md)|[freelist](../standard-library/freelist-class.md) オブジェクトを最長値ゼロまでに制限する最大クラス オブジェクトを記述します。|
|[max_unbounded](../standard-library/max-unbounded-class.md)|[freelist](../standard-library/freelist-class.md) オブジェクトの最長値を制限しない最大クラス オブジェクトを記述します。|
|[max_variable_size](../standard-library/max-variable-size-class.md)|割り当てたメモリ ブロックの数にほぼ比例した最長値までに [freelist](../standard-library/freelist-class.md) オブジェクトを制御する、最大クラス オブジェクトを記述します。|
|[rts_alloc](../standard-library/rts-alloc-class.md)|rts_alloc クラス テンプレートは、キャッシュ インスタンスの配列を保持する[フィルター](../standard-library/allocators-header.md)を記述し、コンパイル時ではなく実行時に割り当てと割り当て解除に使用するインスタンスを決定します。|
|[sync_none](../standard-library/sync-none-class.md)|同期を提供しない同期フィルターを記述します。|
|[sync_per_container](../standard-library/sync-per-container-class.md)|アロケーター オブジェクトごとに個別のキャッシュ オブジェクトを提供する同期フィルターを記述します。|
|[sync_per_thread](../standard-library/sync-per-thread-class.md)|スレッドごとに個別のキャッシュ オブジェクトを提供する同期フィルターを記述します。|
|[sync_shared](../standard-library/sync-shared-class.md)|すべてのアロケーターによって共有されているキャッシュ オブジェクトへのアクセスを制御するためにミューテックスを使用する同期フィルターを表します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<allocators>

**名前空間:** stdext

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)
