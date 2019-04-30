---
title: is_error_code_enum 構造体
ms.date: 11/04/2016
f1_keywords:
- future/std::is_error_code_enum
ms.assetid: 84ae4b99-66d2-41ba-9b50-645fcbe14630
ms.openlocfilehash: 54def287aa6b4bbb06d88006615b5df45b482051
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62336584"
---
# <a name="iserrorcodeenum-structure"></a>is_error_code_enum 構造体

[future_errc](../standard-library/future-enums.md#future_errc) が [error_code](../standard-library/error-code-class.md) の格納に適していることを示す特殊化です。

## <a name="syntax"></a>構文

```cpp
template <>
struct is_error_code_enum<Future_errc> : public true_type;
```

## <a name="requirements"></a>必要条件

**ヘッダー:** \<将来 >

**名前空間:** std

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<future>](../standard-library/future.md)<br/>
