---
description: '詳細情報: bad_any_cast クラス'
title: bad_any_cast クラス
ms.date: 04/04/2019
f1_keywords:
- any/std::bad_any_cast
- any/std::bad_any_cast::what
helpviewer_keywords:
- any/std::bad_any_cast
- any/std::bad_any_cast::what
ms.openlocfilehash: 5b38405bf1fc826592995df4037c5853e88ad9eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321628"
---
# <a name="bad_any_cast-class"></a>bad_any_cast クラス

によってスローされたオブジェクトが失敗しました `any_cast` 。

## <a name="syntax"></a>構文

```cpp
class bad_any_cast
```

### <a name="member-functions"></a>メンバー関数

|名前|説明|
|-|-|
|[結果](#what)|型を返します。|

## <a name="what"></a><a name="what"></a> 結果

型を返します。

```cpp
const char* what() const noexcept override;
```
