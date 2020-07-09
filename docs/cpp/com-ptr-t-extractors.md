---
title: _com_ptr_t 抽出
description: _Com_ptr_t クラスの抽出演算子について説明します。
ms.date: 07/07/2020
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
ms.openlocfilehash: e7b06bb11ab34a1a1a7f6fab98d177821f60b20c
ms.sourcegitcommit: e17cc8a478b51739d67304d7d82422967b35f716
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2020
ms.locfileid: "86127847"
---
# <a name="_com_ptr_t-extractors"></a>`_com_ptr_t`器

**Microsoft 固有の仕様**

カプセル化された COM インターフェイス ポインターを抽出します。

## <a name="syntax"></a>構文

```c++
operator Interface*( ) const throw( );
operator Interface&( ) const;
Interface& operator*( ) const;
Interface* operator->( ) const;
Interface** operator&( ) throw( );
operator bool( ) const throw( );
```

## <a name="remarks"></a>解説

- **`operator Interface*`** カプセル化されたインターフェイスポインターを返します。 NULL の場合もあります。

- **`operator Interface&`** カプセル化されたインターフェイスポインターへの参照を返し、ポインターが NULL の場合はエラーを発行します。

- **`operator*`** スマートポインターオブジェクトが、逆参照時に実際にカプセル化されたインターフェイスであるかのように動作することを許可します。

- **`operator->`** スマートポインターオブジェクトが、逆参照時に実際にカプセル化されたインターフェイスであるかのように動作することを許可します。

- **`operator&`** カプセル化されたインターフェイスポインターをすべて解放し、NULL で置き換えて、カプセル化されたポインターのアドレスを返します。 この演算子を使用すると、インターフェイスポインターを返す*out*パラメーターを持つ関数に、アドレスを指定してスマートポインターを渡すことができます。

- **`operator bool`** スマートポインターオブジェクトを条件式で使用できるようにします。 この演算子は、ポインターが NULL でない場合に TRUE を返します。

  > [!NOTE]
  > **`operator bool`** はとして宣言されていないため **`explicit`** 、 `_com_ptr_t` はに暗黙的に変換可能で **`bool`** 、任意のスカラー型に変換できます。 これにより、コードに予期しない結果が生じる可能性があります。 この変換の意図しない使用を防ぐために、[コンパイラの警告 (レベル 4) C4800](../error-messages/compiler-warnings/compiler-warning-level-3-c4800.md)を有効にします。

## <a name="see-also"></a>関連項目

[_com_ptr_t クラス](../cpp/com-ptr-t-class.md)
