---
title: Concurrency::graphics 名前空間
ms.date: 11/04/2016
f1_keywords:
- AMP_GRAPHICS/Concurrency
ms.assetid: 4529d3b1-d7da-4ffb-82bf-080915e0f23e
ms.openlocfilehash: ef61c93e062b375377a0afe62aa7f622f6c0d4ac
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57326537"
---
# <a name="concurrencygraphics-namespace"></a>Concurrency::graphics 名前空間

graphics 名前空間は、グラフィックス プログラミング用に設計された型と関数を提供します。

## <a name="syntax"></a>構文

```
namespace graphics;
```

## <a name="members"></a>メンバー

### <a name="namespaces"></a>名前空間

|名前|説明|
|----------|-----------------|
|[Concurrency::graphics::direct3d 名前空間](concurrency-graphics-direct3d-namespace.md)|Direct3D の相互運用のための関数を提供します。|

### <a name="typedefs"></a>Typedef

|名前|説明|
|----------|-----------------|
|`uint`|要素型[uint_2 クラス](uint-2-class.md)、 [uint_3 クラス](uint-3-class.md)、および[uint_4 クラス](uint-4-class.md)します。 `typedef unsigned int uint;` として定義されます。|

### <a name="enumerations"></a>列挙

|名前|説明|
|----------|-----------------|
|[address_mode 列挙型](concurrency-graphics-namespace-enums.md#address_mode)します。|テクスチャ サンプリングでサポートされているアドレス モードを指定します。|
|[filter_mode 列挙型](concurrency-graphics-namespace-enums.md#filter_mode)|テクスチャ サンプリングでサポートされているフィルター モードを指定します。|

### <a name="classes"></a>クラス

|名前|説明|
|----------|-----------------|
|[texture クラス](texture-class.md)|テクスチャは範囲ドメイン内の accelerator_view についてのデータ集合体です。 これは、範囲ドメインの各要素に対して 1 つずつの変数のコレクションです。 各変数は、対応する C++ のプリミティブ型 (unsigned int、int、float、double)、またはスカラー型の norm、または unorm (concurrency::graphics で定義)、または concurrency::graphics で定義されている有効な short ベクター型の値を保持します。|
|[writeonly_texture_view クラス](writeonly-texture-view-class.md)|writeonly_texture_view はテクスチャへの writeonly アクセスを提供します。|
|[double_2 クラス](double-2-class.md)|2 個の `double` 値の short ベクターを表します。|
|[double_3 クラス](double-3-class.md)|3 の short ベクターを表します`double`値。|
|[double_4 クラス](double-4-class.md)|4 の short ベクターを表します`double`値。|
|[float_2 クラス](float-2-class.md)|2 個の `float` 値の short ベクターを表します。|
|[float_3 クラス](float-3-class.md)|3 の short ベクターを表します`float`値。|
|[float_4 クラス](float-4-class.md)|4 の short ベクターを表します`float`値。|
|[int_2 クラス](int-2-class.md)|2 個の `int` 値の short ベクターを表します。|
|[int_3 クラス](int-3-class.md)|3 の short ベクターを表します`int`値。|
|[int_4 クラス](int-4-class.md)|4 の short ベクターを表します`int`値。|
|[norm_2 クラス](norm-2-class.md)|2 個の `norm` 値の short ベクターを表します。|
|[norm_3 クラス](norm-3-class.md)|3 の short ベクターを表します`norm`値。|
|[norm_4 クラス](norm-4-class.md)|4 の short ベクターを表します`norm`値。|
|[uint_2 クラス](uint-2-class.md)|2 個の `uint` 値の short ベクターを表します。|
|[uint_3 クラス](uint-3-class.md)|3 の short ベクターを表します`uint`値。|
|[uint_4 クラス](uint-4-class.md)|4 の short ベクターを表します`uint`値。|
|[unorm_2 クラス](unorm-2-class.md)|2 個の `unorm` 値の short ベクターを表します。|
|[unorm_3 クラス](unorm-3-class.md)|3 の short ベクターを表します`unorm`値。|
|[unorm_4 クラス](unorm-4-class.md)|4 の short ベクターを表します`unorm`値。|
|[sampler クラス](sampler-class.md)|テクスチャ サンプリングに使用するサンプラー構成を表します。|
|[short_vector 構造体](short-vector-structure.md)|値の short ベクターの基本的な実装を提供します。|
|[short_vector_traits 構造体](short-vector-traits-structure.md)|short ベクターの長さと型の取得を提供します。|
|[texture_view クラス](texture-view-class.md)|テクスチャへの読み取りアクセスおよび書き込みアクセスを提供します。|

### <a name="functions"></a>関数

|名前|説明|
|----------|-----------------|
|[copy](concurrency-graphics-namespace-functions.md#copy)|オーバーロードされます。 ソース テクスチャの内容をターゲット ホスト バッファーにコピーします。|
|[copy_async](concurrency-graphics-namespace-functions.md#copy_async)|オーバーロードされます。 ソース テクスチャの内容をターゲット ホスト バッファーに非同期にコピーします。|

## <a name="requirements"></a>必要条件

**ヘッダー:** amp_graphics.h

**名前空間:** 並行性

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
