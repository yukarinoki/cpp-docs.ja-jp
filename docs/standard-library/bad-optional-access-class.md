---
title: bad_optional_access クラス
ms.date: 11/04/2016
f1_keywords:
- optional/std::bad_optional_access
ms.assetid: 89a3b805-ab60-4858-b772-5855130c11b1
ms.openlocfilehash: f898d1e30dd173339192bdb3b75581d12b62fca7
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68269144"
---
# <a name="badoptionalaccess-class"></a>bad_optional_access クラス

値にアクセスする試みが行われる場所のような状況を報告する例外としてスローするオブジェクトの種類を定義する`optional`値が含まれていないオブジェクト。

## <a name="syntax"></a>構文

```cpp
class bad_optional_access : public exception
{
    public: bad_optional_access();
};
```
