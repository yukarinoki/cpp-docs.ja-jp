---
title: allocate
ms.date: 11/04/2016
f1_keywords:
- allocate_cpp
helpviewer_keywords:
- __declspec keyword [C++], allocate
- allocate __declspec keyword
ms.assetid: 67828b31-de60-4c0e-b0a6-ef3aab22641d
ms.openlocfilehash: 0bf31423cd76c838cbeffa7458bbccb89592bf43
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227622"
---
# <a name="allocate"></a>allocate

**Microsoft 固有の仕様**

**`allocate`** 宣言指定子は、データ項目が割り当てられるデータセグメントの名前を指定します。

## <a name="syntax"></a>構文

> **`__declspec(allocate("`***segname* **`))`***宣言子*

## <a name="remarks"></a>解説

名前*segname*は、次のいずれかのプラグマを使用して宣言する必要があります。

- [code_seg](../preprocessor/code-seg.md)

- [const_seg](../preprocessor/const-seg.md)

- [data_seg](../preprocessor/data-seg.md)

- [init_seg](../preprocessor/init-seg.md)

- [下](../preprocessor/section.md)

## <a name="example"></a>例

```cpp
// allocate.cpp
#pragma section("mycode", read)
__declspec(allocate("mycode"))  int i = 0;

int main() {
}
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[`__declspec`](../cpp/declspec.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
