---
title: '&lt;new&gt;'
ms.date: 11/04/2016
f1_keywords:
- <new>
helpviewer_keywords:
- new header
ms.assetid: 218e2a15-34e8-4ef3-9122-1e90eccf8559
ms.openlocfilehash: b6f1cc45f9666fc0fbd2332ac7bb7e539ec77cd3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223650"
---
# <a name="ltnewgt"></a>&lt;new&gt;

プログラムの制御下でストレージの割り当てと解放を制御するいくつかの型および関数を定義します。 また、ストレージ管理エラーに関するレポート用のコンポーネントを定義します。

## <a name="syntax"></a>構文

```cpp
#include <new>
```

## <a name="remarks"></a>Remarks

このヘッダーで宣言されている関数の一部は置換できます。 実装の際に既定のバージョンが提供されます。既定バージョンの動作については、このドキュメントで説明します。 ただし、プログラムで同じシグネチャを持つ関数を定義して、リンク時に既定のバージョンを置換することもできます。 置換バージョンは、このドキュメントで説明する要件を満たす必要があります。

### <a name="objects"></a>オブジェクト

|||
|-|-|
|[nothrow](../standard-library/new-functions.md#nothrow)|引数として使用するオブジェクトを提供します、 **nothrow**のバージョンの**新しい**と**削除**します。|

### <a name="typedefs"></a>Typedef

|型名|説明|
|-|-|
|[new_handler](../standard-library/new-typedefs.md#new_handler)|新しいハンドラーとして使用するのに適した関数を指す型。|

### <a name="functions"></a>関数

|関数|説明|
|-|-|
|[set_new_handler](../standard-library/new-functions.md#set_new_handler)|メモリ割り当ての試行に新たに失敗した場合に呼び出されるユーザー関数をインストールします。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator delete](../standard-library/new-operators.md#op_delete)|個々のオブジェクトに対するストレージの割り当てを解除する削除式によって呼び出される関数。|
|[operator delete&#91;&#93;](../standard-library/new-operators.md#op_delete_arr)|オブジェクトの配列に対するストレージの割り当てを解除する削除式によって呼び出される関数。|
|[operator new](../standard-library/new-operators.md#op_new)|個々のオブジェクトにストレージを割り当てる新しい式によって呼び出される関数。|
|[operator new&#91;&#93;](../standard-library/new-operators.md#op_new_arr)|オブジェクトの配列にストレージを割り当てる新しい式によって呼び出される関数。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[bad_alloc クラス](../standard-library/bad-alloc-class.md)|このクラスは、割り当て要求が成功しなかったことを示すためにスローされる例外を記述します。|
|[nothrow_t クラス](../standard-library/nothrow-t-structure.md)|このクラスは、新しい演算子への関数のパラメーターとして使用され、この関数が割り当ての失敗を報告するには、例外をスローするのではなく null ポインターを返す必要があることを示します。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
