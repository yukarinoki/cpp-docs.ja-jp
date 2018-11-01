---
title: once_flag 構造体
ms.date: 09/17/2018
f1_keywords:
- mutex/std::once_flag
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
ms.openlocfilehash: 004a5545e2eccab83b0846e2ae30b88c8431c99d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481972"
---
# <a name="onceflag-structure"></a>once_flag 構造体

表す、**構造体**テンプレート関数で使用されている[call_once](../standard-library/mutex-functions.md#call_once)ように初期化するコードは 1 回だけ呼び出す、複数の実行スレッドがある場合でもです。

## <a name="syntax"></a>構文

構造体 once_flag {constexpr once_flag() noexcept;};

## <a name="remarks"></a>Remarks

`once_flag` **構造体**既定のコンス トラクターのみです。

`once_flag` 型のオブジェクトは、作成することはできますがコピーはできません。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<mutex >

**名前空間:** std

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>
