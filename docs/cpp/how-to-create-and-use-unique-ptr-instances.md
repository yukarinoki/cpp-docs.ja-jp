---
description: '詳細については、「方法: unique_ptr インスタンスを作成して使用する」を参照してください。'
title: '方法: unique_ptr インスタンスを作成して使用する'
ms.custom: how-to
ms.date: 11/19/2018
ms.topic: conceptual
ms.assetid: 9a373030-e587-452f-b9a5-c5f9d58b7673
ms.openlocfilehash: a53b3a9704c62803b50c9bde2c7db70c190a8008
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97268666"
---
# <a name="how-to-create-and-use-unique_ptr-instances"></a>方法: unique_ptr インスタンスを作成して使用する

[Unique_ptr](../standard-library/unique-ptr-class.md)はそのポインターを共有しません。 別のにコピーし `unique_ptr` たり、値渡しで関数に渡したり、コピーの作成を必要とする任意の C++ 標準ライブラリアルゴリズムで使用したりすることはできません。 `unique_ptr` ができるのは移動だけです。 この場合、メモリ リソースの所有権は別の `unique_ptr` に移動し、元の `unique_ptr` はそれ以降、所有権を失います。 複数の所有者がオブジェクトを所有するとプログラム ロジックが複雑になるため、所有者を 1 人に制限することをお勧めします。 したがって、プレーンな C++ オブジェクト用のスマートポインターが必要な場合は `unique_ptr` 、を使用し、を構築するときに `unique_ptr` [make_unique](../standard-library/memory-functions.md#make_unique) ヘルパー関数を使用します。

次の図では、2 つの `unique_ptr` のインスタンス間での所有権の移転を示します。

![一意の&#95;ptr の所有権の移動](media/unique_ptr.png "一意の&#95;ptr の所有権の移動")

`unique_ptr` は、C++ 標準ライブラリのヘッダーで定義されてい `<memory>` ます。 これは生のポインターと同じように効率的であり、C++ 標準ライブラリコンテナーで使用できます。 の移動コンストラクターによって `unique_ptr` コピー操作が不要になるため、C++ 標準ライブラリコンテナーにインスタンスを追加することは効率的です `unique_ptr` 。

## <a name="example-1"></a>例 1

次の例では、`unique_ptr` インスタンスを作成し、関数間で渡す方法を示します。

[!code-cpp[stl_smart_pointers#210](codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_1.cpp)]

これらの例は、`unique_ptr` の基本的な機能として、移動はできるが、コピーはできないことを示しています。 「移動」は `unique_ptr` に所有権を移転し、元の `unique_ptr` をリセットします。

## <a name="example-2"></a>例 2

次の例では、`unique_ptr` インスタンスを作成し、ベクター内で使用する方法を示します。

[!code-cpp[stl_smart_pointers#211](codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_2.cpp)]

ループの範囲で、`unique_ptr` が参照によって渡されることに注意してください。 ここで値によって渡そうとすると、`unique_ptr` コピー コンストラクターが削除されるため、コンパイラによってエラーがスローされます。

## <a name="example-3"></a>例 3

次の例では、クラス メンバーである `unique_ptr` を初期化する方法を示しています。

[!code-cpp[stl_smart_pointers#212](codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_3.cpp)]

## <a name="example-4"></a>例 4

[Make_unique](../standard-library/memory-functions.md#make_unique)を使用してを配列に作成することはでき `unique_ptr` ますが、を使用し `make_unique` て配列要素を初期化することはできません。

[!code-cpp[stl_smart_pointers#213](codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_4.cpp)]

その他の例については、「 [make_unique](../standard-library/memory-functions.md#make_unique)」を参照してください。

## <a name="see-also"></a>関連項目

[スマートポインター (最新の C++)](smart-pointers-modern-cpp.md)<br/>
[make_unique](../standard-library/memory-functions.md#make_unique)
