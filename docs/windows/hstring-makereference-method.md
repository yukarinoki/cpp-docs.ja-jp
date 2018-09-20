---
title: Hstring::makereference メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::MakeReference
dev_langs:
- C++
ms.assetid: 9e1fd2b2-66ad-4a50-b647-a20ab10e522f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ebc8632d273e650cf11e70177bbfbeb0e90e8601
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394856"
---
# <a name="hstringmakereference-method"></a>HString::MakeReference メソッド

作成、`HStringReference`オブジェクト指定した文字列パラメーターから。

## <a name="syntax"></a>構文

```cpp
template<unsigned int sizeDest>
    static HStringReference MakeReference(
              wchar_t const (&str)[ sizeDest]);

    template<unsigned int sizeDest>
    static HStringReference MakeReference(
              wchar_t const (&str)[sizeDest],
              unsigned int len);
```

### <a name="parameters"></a>パラメーター

*sizeDest*<br/>
変換先のサイズを指定するテンプレート パラメーター`HStringReference`バッファー。

*str*<br/>
ワイド文字の文字列への参照。

*len*<br/>
最大長、 *str*この操作で使用するパラメーターのバッファー。 場合、 *len*パラメーターが指定されていない全体*str*パラメーターを使用します。

## <a name="return-value"></a>戻り値

`HStringReference`オブジェクトの値が指定したのと同じ*str*パラメーター。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[HString クラス](../windows/hstring-class.md)