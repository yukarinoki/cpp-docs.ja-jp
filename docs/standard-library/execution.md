---
title: 実行&gt; の &lt;
ms.date: 04/18/2019
f1_keywords:
- <execution>
- std::<execution>
helpviewer_keywords:
- execution header
ms.openlocfilehash: 81e9aa63265c367412fda709aacd5ca3953e9fdf
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445036"
---
# <a name="ltexecutiongt"></a>実行&gt; の &lt;

並列アルゴリズムの実行ポリシーについて説明します。

## <a name="syntax"></a>構文

```
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

|||
|-|-|
|[is_execution_policy 構造体](is-execution-policy-struct.md)|は、あいまいなオーバーロードの解決への参加から、関数シグネチャを除外するための実行ポリシーを検出します。|
|[parallel_policy クラス](parallel-policy-class.md)|並列アルゴリズムのオーバーロードを明確にするための一意の型として使用され、並列アルゴリズムの実行が並列化される可能性があることを示します。|
|[parallel_unsequenced_policy クラス](parallel-unsequenced-policy-class.md)|並列アルゴリズムのオーバーロードを明確にするための一意の型として使用され、並列アルゴリズムの実行が並列化され、ベクター化される可能性があることを示します。|
|[sequenced_policy クラス](sequenced-policy-class.md)|並列アルゴリズムのオーバーロードを明確にするために一意の型として使用され、並列アルゴリズムの実行を並列化できないようにする必要があります。|

## <a name="requirements"></a>要件

**ヘッダー:** 実行の \<>

**名前空間:** stdext

## <a name="see-also"></a>参照

[ヘッダー ファイル リファレンス](cpp-standard-library-header-files.md)\
[C++ 標準ライブラリ内のスレッド セーフ](thread-safety-in-the-cpp-standard-library.md)\
[C++ 標準ライブラリ リファレンス](cpp-standard-library-reference.md)
