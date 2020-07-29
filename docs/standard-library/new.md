---
title: '&lt;新規&gt;'
ms.date: 11/04/2016
f1_keywords:
- <new>
helpviewer_keywords:
- new header
ms.assetid: 218e2a15-34e8-4ef3-9122-1e90eccf8559
ms.openlocfilehash: 2a35a7b4d9581a11d889f3e66d0179c553c4fc25
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212164"
---
# <a name="ltnewgt"></a>&lt;新規&gt;

プログラムの制御下でストレージの割り当てと解放を制御するいくつかの型および関数を定義します。 また、ストレージ管理エラーに関するレポート用のコンポーネントを定義します。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<new>

**名前空間:** std

## <a name="remarks"></a>解説

このヘッダーで宣言されている関数の一部は置換できます。 実装の際に既定のバージョンが提供されます。既定バージョンの動作については、このドキュメントで説明します。 ただし、プログラムで同じシグネチャを持つ関数を定義して、リンク時に既定のバージョンを置換することもできます。 置換バージョンは、このドキュメントで説明する要件を満たす必要があります。

## <a name="members"></a>メンバー

### <a name="objects"></a>Objects

|||
|-|-|
|[nothrow](../standard-library/new-functions.md#nothrow)|およびのバージョンの引数として使用されるオブジェクトを提供し **`nothrow`** **`new`** **`delete`** ます。|

### <a name="typedefs"></a>Typedefs

|||
|-|-|
|[new_handler](../standard-library/new-typedefs.md#new_handler)|新しいハンドラーとして使用するのに適した関数を指す型。|
|[hardware_constructive_interference_size](../standard-library/new-typedefs.md#hardware_destructive_interference_size)||
|[hardware_destructive_interference_size](../standard-library/new-typedefs.md#hardware_destructive_interference_size)||

### <a name="functions"></a>関数

|||
|-|-|
|[get_new_handler](../standard-library/new-functions.md#get_new_handler)||
|[launder](../standard-library/new-functions.md#launder)||
|[set_new_handler](../standard-library/new-functions.md#set_new_handler)|メモリ割り当ての試行に新たに失敗した場合に呼び出されるユーザー関数をインストールします。|

### <a name="operators"></a>オペレーター

|||
|-|-|
|[delete 演算子](../standard-library/new-operators.md#op_delete)|個々のオブジェクトに対するストレージの割り当てを解除する削除式によって呼び出される関数。|
|[operator delete&#91;&#93;](../standard-library/new-operators.md#op_delete_arr)|オブジェクトの配列に対するストレージの割り当てを解除する削除式によって呼び出される関数。|
|[new 演算子](../standard-library/new-operators.md#op_new)|個々のオブジェクトにストレージを割り当てる新しい式によって呼び出される関数。|
|[operator new&#91;&#93;](../standard-library/new-operators.md#op_new_arr)|オブジェクトの配列にストレージを割り当てる新しい式によって呼び出される関数。|

### <a name="enums"></a>列挙型

|||
|-|-|
|[align_val_t](../standard-library/new-operators.md#op_align_val_t)||

### <a name="classes"></a>クラス

|||
|-|-|
|[bad_alloc クラス](../standard-library/bad-alloc-class.md)|このクラスは、割り当て要求が成功しなかったことを示すためにスローされる例外を記述します。|
|[bad_array_new_length クラス](../standard-library/bad-array-new-length.md)||
|[nothrow_t クラス](../standard-library/nothrow-t-structure.md)|このクラスは、新しい演算子への関数のパラメーターとして使用され、この関数が割り当ての失敗を報告するには、例外をスローするのではなく null ポインターを返す必要があることを示します。|

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
