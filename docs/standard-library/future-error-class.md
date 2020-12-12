---
description: '詳細情報: future_error クラス'
title: future_error クラス
ms.date: 11/04/2016
f1_keywords:
- future/std::future_error
ms.assetid: 6071c545-ac2a-49ef-9967-07b0125da861
ms.openlocfilehash: c7dc99ea842cd13658c13a5c2492bda3d853302f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324214"
---
# <a name="future_error-class"></a>future_error クラス

[future](../standard-library/future-class.md) オブジェクトを管理する型のメソッドによってスローされる例外オブジェクトを記述します。

## <a name="syntax"></a>構文

```cpp
class future_error : public logic_error {
public:
    future_error(error_code code);

const error_code& code() const throw();

const char *what() const throw();

};
```

## <a name="requirements"></a>必要条件

**ヘッダー:**\<future>

**名前空間:** std

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[logic_error クラス](../standard-library/logic-error-class.md)\
[error_code クラス](../standard-library/error-code-class.md)
