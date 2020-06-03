---
title: Platform::Collections 名前空間
ms.date: 01/18/2018
ms.topic: reference
f1_keywords:
- collection/Platform::Collections
helpviewer_keywords:
- Platform::Collections Namespace
ms.assetid: b5042864-5f22-40b7-b7a5-c0691f65cc47
ms.openlocfilehash: ab6b78f1b88c586a11276d36387fb42ea6ee667f
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032422"
---
# <a name="platformcollections-namespace"></a>Platform::Collections 名前空間

プラットフォーム::コレクション名前空間`Map`には、、、、、、`MapView`およびクラス`Vector``VectorView`が含まれています。 これらのクラスは、 [Windows::Foundation::Collections](/uwp/api/windows.foundation.collections) 名前空間に定義されている、対応するインターフェイスの具象実装です。 具体的なコレクション型は、(Javascript または C# で書かれたプログラムが C ++ コンポーネントを呼び出すなど) ABI を越えて移植することはできませんが、対応するインターフェイスの型に暗黙的に変換できます。 たとえば、コレクションを設定して返すパブリック メソッドを実装する場合は、 [Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) を使用して内部的にコレクションを実装し、 [Windows::Foundation::Collections::IVector](/uwp/api/windows.foundation.collections.ivector-1) を戻り値の型として使用します。 詳細については、「 コレクション」および[「](../cppcx/collections-c-cx.md) [C++ での Windows ランタイム コンポーネントの作成](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)」を参照してください。

Platform::Collections::Vector は [std::vector](../standard-library/vector-class.md) から構築でき、 [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) は [std::map](../standard-library/map-class.md)から構築できます。

さらに、プラットフォーム::コレクション名前空間は、バック挿入と入力反復子、および`Vector`反復子のサポートを`VectorView`提供します。

プラットフォーム::コレクション`#include`名前空間で型を使用するには、collection.h ヘッダーを含める必要があります。

## <a name="syntax"></a>構文

```cpp
#include <collection.h>
using namespace Platform::Collections;
```

### <a name="members"></a>メンバー

この名前空間には、次のメンバーが含まれます。

|名前|説明|
|----------|-----------------|
|[Platform::Collections::BackInsertIterator クラス](../cppcx/platform-collections-backinsertiterator-class.md)|コレクションの末尾に要素を挿入する反復子を表します。|
|[Platform::Collections::InputIterator クラス](../cppcx/platform-collections-inputiterator-class.md)|コレクションの先頭に要素を挿入する反復子を表します。|
|[Platform::Collections::Map クラス](../cppcx/platform-collections-map-class.md)|キーによりアクセスされるキーと値のペアの変更可能なコレクションを表します。 [std::map](../standard-library/map-class.md)に似ています。|
|[Platform::Collections::MapView クラス](../cppcx/platform-collections-mapview-class.md)|キーによりアクセスされるキーと値のペアの読み取り専用のコレクションを表します。|
|[Platform::Collections::Vector クラス](../cppcx/platform-collections-vector-class.md)|要素の変更可能なシーケンスを表します。 [std::vector](../standard-library/vector-class.md)に似ています。|
|[Platform::Collections::VectorIterator クラス](../cppcx/platform-collections-vectoriterator-class.md)|`Vector` コレクションを走査する反復子を表します。|
|[Platform::Collections::VectorView クラス](../cppcx/platform-collections-vectorview-class.md)|要素の読み取り専用のシーケンスを表します。|
|[プラットフォーム:コレクション::ベクタービュー反復器クラス](../cppcx/platform-collections-vectorviewiterator-class.md)|`VectorView` コレクションを走査する反復子を表します。|

## <a name="inheritance-hierarchy"></a>継承階層

[プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)

### <a name="requirements"></a>必要条件

**メタデータ:** プラットフォーム.winmd

**名前空間:** Platform::Collections

**コンパイラ オプション:** /ZW

## <a name="see-also"></a>関連項目

[プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)
