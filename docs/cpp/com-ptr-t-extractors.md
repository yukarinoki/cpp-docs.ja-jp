---
title: _com_ptr_t 抽出
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::operatorInterface&
- _com_ptr_t::operatorbool
- _com_ptr_t::operator->
- _com_ptr_t::operator*
helpviewer_keywords:
- operator Interface& [C++]
- '* operator [C++], with specific objects'
- operator& [C++]
- operator* [C++]
- -> operator [C++], with specific objects
- '& operator [C++], with specific objects'
- operator Interface* [C++]
- operator * [C++]
- operator->
- operator bool
- extractors, _com_ptr_t class
- extractors [C++]
ms.assetid: 194b9e0e-123c-49ff-a187-0a7fcd68145a
ms.openlocfilehash: 31ac39104c041d1d119f6cd06de5f9c4a620dac0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190028"
---
# <a name="_com_ptr_t-extractors"></a>_com_ptr_t 抽出

**Microsoft 固有の仕様**

カプセル化された COM インターフェイス ポインターを抽出します。

## <a name="syntax"></a>構文

```
operator Interface*( ) const throw( );
operator Interface&( ) const;
Interface& operator*( ) const;
Interface* operator->( ) const;
Interface** operator&( ) throw( );
operator bool( ) const throw( );
```

## <a name="remarks"></a>解説

- **Operator interface** <strong>\*</strong>は、カプセル化されたインターフェイスポインターを返します。 NULL の場合もあります。

- **Operator インターフェイス &** カプセル化されたインターフェイスポインターへの参照を返し、ポインターが NULL の場合はエラーを発行します。

- **operator** <strong>\*</strong>演算子を使用すると、スマートポインターオブジェクトは、逆参照時に実際にカプセル化されたインターフェイスのように動作します。

- **演算子->** スマートポインターオブジェクトが、逆参照時に実際にカプセル化されたインターフェイスであるかのように動作することを許可します。

- **& 演算子**カプセル化されたインターフェイスポインターをすべて解放し、NULL で置き換えて、カプセル化されたポインターのアドレスを返します。 これにより、インターフェイスポインターを返す*out*パラメーターを持つ関数に、アドレスを使用してスマートポインターを渡すことができます。

- **bool 演算子**スマートポインターオブジェクトを条件式で使用できるようにします。 この演算子は、ポインターが NULL でない場合に TRUE を返します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_com_ptr_t クラス](../cpp/com-ptr-t-class.md)
