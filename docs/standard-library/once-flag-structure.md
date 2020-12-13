---
description: '詳細情報: once_flag 構造'
title: once_flag 構造体
ms.date: 09/17/2018
f1_keywords:
- mutex/std::once_flag
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
ms.openlocfilehash: 4419353e68da5929d8abed9b2c718438855057e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338001"
---
# <a name="once_flag-structure"></a>once_flag 構造体

**`struct`** 実行の複数のスレッドが存在する場合でも、初期化コードが1回だけ呼び出されるようにするために、テンプレート関数 [call_once](../standard-library/mutex-functions.md#call_once)と共に使用されるを表します。

## <a name="syntax"></a>構文

構造体 once_flag {constexpr once_flag () noexcept;};

## <a name="remarks"></a>解説

には `once_flag` **`struct`** 既定のコンストラクターのみがあります。

`once_flag` 型のオブジェクトは、作成することはできますがコピーはできません。

## <a name="requirements"></a>要件

**ヘッダー:**\<mutex>

**名前空間:** std

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
