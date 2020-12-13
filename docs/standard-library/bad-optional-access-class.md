---
description: '詳細情報: bad_optional_access クラス'
title: bad_optional_access クラス
ms.date: 08/06/2019
f1_keywords:
- optional/std::bad_optional_access
ms.openlocfilehash: e3439c53766a1890592bde8ed449f5ff2779f347
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132757"
---
# <a name="bad_optional_access-class"></a>bad_optional_access クラス

値を含まないオブジェクトの値にアクセスしようとした状況を報告するために、例外としてスローされるオブジェクトの型を定義し `optional` ます。

## <a name="syntax"></a>構文

```cpp
class bad_optional_access : public exception
{
public:
    bad_optional_access() noexcept;
    bad_optional_access(const bad_optional_access&) noexcept;
    bad_optional_access& operator=(const bad_optional_access&) noexcept;
    const char* what() const noexcept override;
};
```

## <a name="see-also"></a>関連項目

[\<optional>](optional.md)\
[optional クラス](optional-class.md)
