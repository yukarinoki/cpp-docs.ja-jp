---
description: '詳細情報: &lt; 実行&gt;'
title: '&lt;例外&gt;'
ms.date: 01/15/2021
f1_keywords:
- <execution>
- execution/std::execution
- std::execution
helpviewer_keywords:
- execution header
ms.openlocfilehash: 2ffba3ad8620092676588c2a67e36cf8956413ba
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667490"
---
# `<execution>`

並列アルゴリズムの実行ポリシーについて説明します。

## <a name="syntax"></a>Syntax

```cpp
namespace std {
    template<class T> inline constexpr bool is_execution_policy_v = is_execution_policy<T>::value;
}
namespace std::execution {
    inline constexpr sequenced_policy seq { unspecified };
    inline constexpr parallel_policy par { unspecified };
    inline constexpr parallel_unsequenced_policy par_unseq { unspecified };
}
```

### <a name="classes-and-structs"></a>クラスと構造体

|名前|説明|
|-|-|
|[`is_execution_policy` 体型](is-execution-policy-struct.md)|は、あいまいなオーバーロード解決の参加から特定の関数シグネチャを除外する実行ポリシーを検出します。|
|[`parallel_policy` 講義](parallel-policy-class.md)|並列アルゴリズムのオーバーロードを明確にするために、一意の型として使用されます。 並列アルゴリズムの実行が並列化される可能性があることを示します。|
|[`parallel_unsequenced_policy` 講義](parallel-unsequenced-policy-class.md)|並列アルゴリズムのオーバーロードを明確にするために、一意の型として使用されます。 並列アルゴリズムの実行が並列化され、ベクター化される可能性があることを示します。|
|[`sequenced_policy` 講義](sequenced-policy-class.md)|並列アルゴリズムのオーバーロードを明確にするために、一意の型として使用されます。 並列アルゴリズムの実行を並列化できないことを指定します。|

## <a name="requirements"></a>必要条件

**ヘッダー:**\<execution>

**名前空間:** stdext

## <a name="see-also"></a>こちらもご覧ください

[ヘッダーファイルのリファレンス](cpp-standard-library-header-files.md)\
[C++ 標準ライブラリのスレッドセーフ](thread-safety-in-the-cpp-standard-library.md)\
[C++ 標準ライブラリ リファレンス](cpp-standard-library-reference.md)
