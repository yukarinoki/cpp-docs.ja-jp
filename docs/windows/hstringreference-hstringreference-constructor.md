---
title: Hstringreference::hstringreference コンス トラクター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::HStringReference
dev_langs:
- C++
ms.assetid: 29f5fe11-3928-4f60-9861-f0894247bfcb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6123f87abb9922a9736ac56f64d28e78887a0fdd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46403580"
---
# <a name="hstringreferencehstringreference-constructor"></a>HStringReference::HStringReference コンストラクター

新しいインスタンスを初期化、 **HStringReference**クラス。

## <a name="syntax"></a>構文

```cpp
template<unsigned int sizeDest>
HStringReference(wchar_t const (&str)[ sizeDest]) throw();

template<unsigned int sizeDest>
HStringReference(wchar_t const (&str)[ sizeDest],
                 unsigned int len) throw();

HStringReference(HStringReference&& other) throw();
```

### <a name="parameters"></a>パラメーター

*sizeDest*<br/>
変換先のサイズを指定するテンプレート パラメーター **HStringReference**バッファー。

*str*<br/>
ワイド文字の文字列への参照。

*len*<br/>
最大長、 *str*この操作で使用するパラメーターのバッファー。 場合、 *len*パラメーターが指定されていない全体*str*パラメーターを使用します。 場合*len*がより大きい*sizeDest*、 *len*に設定されている*sizeDest*-1。

*other*<br/>
もう 1 つ**HStringReference**オブジェクト。

## <a name="remarks"></a>Remarks

最初のコンス トラクターによって初期化新しい**HStringReference**オブジェクトをパラメーターとして、同じサイズ*str*します。

2 番目のコンス トラクターによって初期化新しい**HStringReference**オブジェクトをパラメーターでサイズ specifeid *len*します。

3 番目のコンス トラクターによって初期化、新しい**HStringReference**オブジェクトの値を*他*パラメーター、し、その後破棄、*他*パラメーター。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[HStringReference クラス](../windows/hstringreference-class.md)