---
title: once_flag 構造体 | Microsoft Docs
ms.custom: ''
ms.date: 09/17/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- mutex/std::once_flag
dev_langs:
- C++
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 67cfbe06461598fbd04e124629399baa63fdd5d9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104336"
---
# <a name="onceflag-structure"></a>once_flag 構造体

表す、**構造体**テンプレート関数で使用されている[call_once](../standard-library/mutex-functions.md#call_once)ように初期化するコードは 1 回だけ呼び出す、複数の実行スレッドがある場合でもです。

## <a name="syntax"></a>構文

構造体 once_flag {constexpr once_flag() noexcept;};

## <a name="remarks"></a>Remarks

`once_flag` **構造体**既定のコンス トラクターのみです。

`once_flag` 型のオブジェクトは、作成することはできますがコピーはできません。

## <a name="requirements"></a>要件

**ヘッダー:** \<mutex >

**名前空間:** std

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>
