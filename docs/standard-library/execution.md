---
title: '&lt;実行&gt;'
ms.date: 04/18/2019
f1_keywords:
- <execution>
- std::<execution>
helpviewer_keywords:
- execution header
ms.openlocfilehash: 3bce34019f9ed4880d72a9d16c3c8b78dde0e0e3
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268424"
---
# <a name="ltexecutiongt"></a>&lt;実行&gt;

並列アルゴリズムの実行ポリシーをについて説明します。

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
|[is_execution_policy 構造体](is-execution-policy-struct.md)|関数のシグネチャをそれ以外の場合にあいまいなオーバー ロードの解決方法への参加から除外するために実行ポリシーを検出します。|
|[parallel_policy クラス](parallel-policy-class.md)|並列アルゴリズムのオーバー ロードあいまいさを解消し、並列アルゴリズムの実行を並列化することがあることを示す一意の型として使用されます。|
|[parallel_unsequenced_policy クラス](parallel-unsequenced-policy-class.md)|並列アルゴリズムの実行の並列化されベクター化ことを示し、並列アルゴリズムのオーバー ロードを明確に一意の型として使用されます。|
|[sequenced_policy クラス](sequenced-policy-class.md)|並列アルゴリズムのオーバー ロードを区別する、並列アルゴリズムの実行を並列いない可能性がありますを必要とする一意の型として使用されます。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<実行 >

**名前空間:** stdext

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](cpp-standard-library-reference.md)
