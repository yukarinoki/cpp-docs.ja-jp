---
title: mem_fun_ref_t クラス
ms.date: 02/21/2019
f1_keywords:
- functional/std::mem_fun_ref_t
helpviewer_keywords:
- mem_fun_ref_t class
ms.assetid: 7dadcac3-8d33-4e4b-a792-81bd53d3df39
ms.openlocfilehash: 0879736863a9b8052d19cc86dc5636ba14bcf993
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240605"
---
# <a name="memfunreft-class"></a>mem_fun_ref_t クラス

使用するアダプター クラスを`non_const`参照引数による初期化時に、単項関数オブジェクトとして呼び出せるようにする引数を受け取らないメンバー関数。 C++ 11、c++ 17 では削除では、非推奨とされます。

## <a name="syntax"></a>構文

```cpp
template <class Result, class Type>
class mem_fun_ref_t : public unary_function<Type, Result> {
    explicit mem_fun_ref_t(
    Result (Type::* _Pm)());

    Result operator()(Type& left) const;
};
```

### <a name="parameters"></a>パラメーター

*_Pm*\
関数オブジェクトに変換されるクラス `Type` のメンバー関数へのポインター。

*左*\
オブジェクトを *_Pm*でメンバー関数が呼び出されます。

## <a name="return-value"></a>戻り値

適合可能な単項関数。

## <a name="remarks"></a>Remarks

テンプレート クラスのコピーを格納する *_Pm*、クラスのメンバー関数へのポインターでなければならない`Type`、プライベート メンバー オブジェクトにします。 そのメンバー関数`operator()`返すよう (**左**. * `_Pm`) ()。

## <a name="example"></a>例

`mem_fun_ref_t` のコンストラクターは通常は直接使用されません。ヘルパー関数 `mem_fun_ref` を使用してメンバー関数を適合させます。 メンバー関数アダプターの使用例については、「[mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref)」を参照してください。
