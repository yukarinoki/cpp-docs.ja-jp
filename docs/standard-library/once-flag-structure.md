---
title: once_flag 構造体
ms.date: 09/17/2018
f1_keywords:
- mutex/std::once_flag
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
ms.openlocfilehash: 55c3f90f72857a4e4cd3f9075ce5bae10e14d218
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87202728"
---
# <a name="once_flag-structure"></a>once_flag 構造体

**`struct`** 実行の複数のスレッドが存在する場合でも、初期化コードが1回だけ呼び出されるようにするために、テンプレート関数[call_once](../standard-library/mutex-functions.md#call_once)と共に使用されるを表します。

## <a name="syntax"></a>構文

構造体 once_flag {constexpr once_flag () noexcept;};

## <a name="remarks"></a>解説

には `once_flag` **`struct`** 既定のコンストラクターのみがあります。

`once_flag` 型のオブジェクトは、作成することはできますがコピーはできません。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<mutex>

**名前空間:** std

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
