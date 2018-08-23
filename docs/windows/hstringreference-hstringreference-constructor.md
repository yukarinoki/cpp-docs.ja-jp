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
ms.openlocfilehash: c13635f4b73ee34de11b8c18b0cdd9943b261a29
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42591186"
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

*sizeDest*  
変換先のサイズを指定するテンプレート パラメーター **HStringReference**バッファー。

*str*  
ワイド文字の文字列への参照。

*len*  
最大長、 *str*この操作で使用するパラメーターのバッファー。 場合、 *len*パラメーターが指定されていない全体*str*パラメーターを使用します。 場合*len*がより大きい*sizeDest*、 *len*に設定されている*sizeDest*-1。

*other*  
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