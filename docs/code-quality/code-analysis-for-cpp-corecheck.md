---
title: C++ Core Guidelines チェッカーリファレンス
ms.date: 03/22/2018
ms.topic: reference
helpviewer_keywords:
- code analysis, C++ core check
ms.assetid: f1429463-136e-41ed-8a75-a8dbf0b4fd89
ms.openlocfilehash: e85ce8baed9a1ef39e0ab759ab86a5b570a42fa6
ms.sourcegitcommit: 6e55aeb538b1c39af754f82d6f7738a18f5aa031
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87389949"
---
# <a name="c-core-guidelines-checker-reference"></a>C++ Core Guidelines チェッカーリファレンス

このセクションでは、C++ Core Guidelines チェッカーの警告を示します。 コード分析の詳細については、「 [ `/analyze` (コード分析)](/cpp/build/reference/analyze-code-analysis) 」および「[クイックスタート: C/c + + のコード分析](../code-quality/quick-start-code-analysis-for-c-cpp.md)」を参照してください。

> [!NOTE]
> いくつかの警告は複数のグループに属しており、すべての警告に完全な参照トピックが含まれているわけではありません。

## <a name="owner_pointer-group"></a>OWNER_POINTER Group

[C26402 DONT_HEAP_ALLOCATE_MOVABLE_RESULT](C26402.md)\
移動コンストラクターがある場合は、ヒープに割り当てられたオブジェクトではなく、スコープを持つオブジェクトを返します。 [C++ Core Guidelines 「R. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr)」を参照してください。

[C26403 RESET_OR_DELETE_OWNER](C26403.md)\
所有者ポインター ' variable ' をリセットまたは明示的に削除 \<T> します。*variable* [C++ Core Guidelines 「R. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr)」を参照してください。

[C26404 DONT_DELETE_INVALID](C26404.md)\
無効な状態にある可能性のある所有者は削除しないでください \<T> 。 [C++ Core Guidelines 「R. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr)」を参照してください。

[C26405 DONT_ASSIGN_TO_VALID](C26405.md)\
有効な状態にある可能性のある所有者には割り当てないでください \<T> 。 [C++ Core Guidelines 「R. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr)」を参照してください。

[C26406 DONT_ASSIGN_RAW_TO_OWNER](C26406.md)\
所有者に生のポインターを割り当てないでください \<T> 。 [C++ Core Guidelines 「R. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr)」を参照してください。

[C26407 DONT_HEAP_ALLOCATE_UNNECESSARILY](C26407.md)\
スコープオブジェクトを優先します。不要なヒープ割り当ては行わないでください。 [C++ Core Guidelines 「R. 5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-scoped)」を参照してください。

[C26429 USE_NOTNULL](C26429.md)\
シンボル '*symbol*' は、null 性がテストされていないため、not_null としてマークできます。 [C++ Core Guidelines 「F. 23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value)」を参照してください。

[C26430 TEST_ON_ALL_PATHS](C26430.md)\
シンボル '*symbol*' は、すべてのパスで null 性がテストされていません。 [C++ Core Guidelines 「F. 23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value)」を参照してください。

[C26431 DONT_TEST_NOTNULL](C26431.md)\
式 '*expr*' の型は既に gsl:: not_null です。 Null 性をテストしないでください。 [C++ Core Guidelines 「F. 23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value)」を参照してください。

## <a name="raw_pointer-group"></a>RAW_POINTER グループ

[C26400 NO_RAW_POINTER_ASSIGNMENT](c26400.md)\
所有者の戻り値を持つ割り当てまたは関数呼び出しの結果を生のポインターに割り当てないでください \<T> 。代わりに owner を使用 \<T> してください。 [C++ Core Guidelines I. 11](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Ri-raw)を参照してください。

[C26401 DONT_DELETE_NON_OWNER](c26401.md)\
所有者ではない生のポインターは削除しないでください \<T> 。 [C++ Core Guidelines I. 11](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Ri-raw)を参照してください。

[C26402 DONT_HEAP_ALLOCATE_MOVABLE_RESULT](C26402.md)\
移動コンストラクターがある場合は、ヒープに割り当てられたオブジェクトではなく、スコープを持つオブジェクトを返します。 [C++ Core Guidelines 「R. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr)」を参照してください。

[C26408 NO_MALLOC_FREE](C26408.md)\
Malloc () と free () を使用しないでください。 nothrow バージョンの new を delete と共に使用してください。 [C++ Core Guidelines 「R. 10](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-mallocfree)」を参照してください。

[C26409 NO_NEW_DELETE](C26409.md)\
New と delete を明示的に呼び出すのは避けてください。代わりに std:: make_unique を使用 \<T> してください。 [C++ Core Guidelines 「R. 11](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-newdelete)」を参照してください。

[C26429 USE_NOTNULL](C26429.md)\
シンボル '*symbol*' は、null 性がテストされていないため、not_null としてマークできます。 [C++ Core Guidelines 「F. 23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value)」を参照してください。

[C26430 TEST_ON_ALL_PATHS](C26430.md)\
シンボル '*symbol*' は、すべてのパスで null 性がテストされていません。 [C++ Core Guidelines 「F. 23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value)」を参照してください。

[C26431 DONT_TEST_NOTNULL](C26431.md)\
式 '*expr*' の型は既に gsl:: not_null です。 Null 性をテストしないでください。 [C++ Core Guidelines 「F. 23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value)」を参照してください。

[C26481 NO_POINTER_ARITHMETIC](C26481.md)\
ポインター演算は使用しないでください。 代わりに span を使用します。 「C++ Core Guidelines の境界」を参照してください[。 1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds).

[C26485 NO_ARRAY_TO_POINTER_DECAY](C26485.md)\
式 '*expr*': 配列からポインターが減衰されていません。 「C++ Core Guidelines の境界」を参照してください[。 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds).

## <a name="unique_pointer-group"></a>UNIQUE_POINTER Group

[C26410 NO_REF_TO_CONST_UNIQUE_PTR](C26410.md)\
パラメーター '*parameter*' は一意のポインターへの参照です `const` 。代わりに const t * または const t& を使用してください。 [C++ Core Guidelines 「R. 32](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-uniqueptrparam).」を参照してください。

[C26411 NO_REF_TO_UNIQUE_PTR](C26411.md)\
パラメーター '*parameter*' は一意のポインターへの参照であり、再割り当てもリセットも行われません。代わりに t * または t& を使用してください。 [C++ Core Guidelines 「R. 33](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-reseat)」を参照してください。

[C26414 RESET_LOCAL_SMART_PTR](C26414.md)\
ローカルスマートポインター '*symbol*' を移動、コピー、再割り当て、またはリセットします。 [C++ Core Guidelines 「R. 5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-scoped)」を参照してください。

[C26415 SMART_PTR_NOT_NEEDED](C26415.md)\
スマートポインターパラメーター '*symbol*' は、含まれているポインターにアクセスするためにのみ使用されます。 代わりに T * または T& を使用してください。 [C++ Core Guidelines 「R. 30](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-smartptrparam)」を参照してください。

## <a name="shared_pointer-group"></a>SHARED_POINTER グループ

[C26414 RESET_LOCAL_SMART_PTR](C26414.md)\
ローカルスマートポインター '*symbol*' を移動、コピー、再割り当て、またはリセットします。 [C++ Core Guidelines 「R. 5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-scoped)」を参照してください。

[C26415 SMART_PTR_NOT_NEEDED](C26415.md)\
スマートポインターパラメーター '*symbol*' は、含まれているポインターにアクセスするためにのみ使用されます。 代わりに T * または T& を使用してください。 [C++ Core Guidelines 「R. 30](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-smartptrparam)」を参照してください。

[C26416 NO_RVALUE_REF_SHARED_PTR](C26416.md)\
共有ポインターパラメーター '*symbol*' は右辺値参照によって渡されます。 代わりに値で渡してください。 [C++ Core Guidelines 「R. 34](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-sharedptrparam-owner)」を参照してください。

[C26417 NO_LVALUE_REF_SHARED_PTR](C26417.md)\
共有ポインターパラメーター '*symbol*' は参照によって渡され、リセットまたは再割り当てされません。 代わりに T * または T& を使用してください。 [C++ Core Guidelines 「R. 35](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-sharedptrparam)」を参照してください。

[C26418 NO_VALUE_OR_CONST_REF_SHARED_PTR](C26418.md)\
共有ポインターパラメーター '*symbol*' はコピーまたは移動されません。 代わりに T * または T& を使用してください。 [C++ Core Guidelines 「R. 36](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-sharedptrparam-const)」を参照してください。

## <a name="declaration-group"></a>宣言グループ

[C26426 NO_GLOBAL_INIT_CALLS](C26426.md)\
グローバル初期化子は、constexpr でない関数 '*symbol*' を呼び出します。 「 [C++ Core Guidelines I. 22](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#i22-avoid-complex-initialization-of-global-objects)」を参照してください。

[C26427 NO_GLOBAL_INIT_EXTERNS](C26427.md)\
グローバル初期化子が extern オブジェクト '*symbol*' にアクセスします。 「 [C++ Core Guidelines I. 22](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#i22-avoid-complex-initialization-of-global-objects)」を参照してください。

[C26444 NO_UNNAMED_RAII_OBJECTS](c26444.md)\
カスタムの構築および破棄によって名前のないオブジェクトを使用しないようにします。 「 [ES: いいえ (try)」を参照してください。名前のないローカル変数を宣言して](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md)ください。

## <a name="class-group"></a>クラスグループ

[C26432 DEFINE_OR_DELETE_SPECIAL_OPS](C26432.md)\
'*Symbol*' 型の既定の操作を定義または削除する場合は、すべてを定義するか削除します。 「 [C++ Core Guidelines c. 21](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c21-if-you-define-or-delete-any-default-operation-define-or-delete-them-all)」を参照してください。

[C26433 OVERRIDE_EXPLICITLY](c26433.md)\
関数 '*symbol*' は ' override ' でマークされなければなりません。 「 [C. 128: 仮想関数では、仮想、オーバーライド、または最終」を厳密に1つ指定する必要があり](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c128-virtual-functions-should-specify-exactly-one-of-virtual-override-or-final)ます。

[C26434 DONT_HIDE_METHODS](C26434.md)\
関数 '*symbol_1*' は、非仮想関数 '*symbol_2*' を非表示にします。 「 [C++ Core Guidelines c. 128](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c128-virtual-functions-should-specify-exactly-one-of-virtual-override-or-final)」を参照してください。

[C26435 SINGLE_VIRTUAL_SPECIFICATION](c26435.md)\
関数 '*symbol*' は、' virtual '、' override '、または ' final ' のいずれか1つだけを指定しなければなりません。 「 [C. 128: 仮想関数では、仮想、オーバーライド、または最終」を厳密に1つ指定する必要があり](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md)ます。

[C26436 NEED_VIRTUAL_DTOR](C26436.md)\
仮想関数を持つ型 '*symbol*' には、パブリック仮想デストラクターまたは保護された非仮想デストラクターのいずれかが必要です。 「 [C++ Core Guidelines c. 35](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c35-a-base-class-destructor-should-be-either-public-and-virtual-or-protected-and-nonvirtual)」を参照してください。

[C26443 NO_EXPLICIT_DTOR_OVERRIDE](c26443.md)\
オーバーライドするデストラクターでは、明示的な ' override ' または ' virtual ' 指定子は使用できません。 「 [C. 128: 仮想関数では、仮想、オーバーライド、または最終」を厳密に1つ指定する必要があり](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md)ます。

## <a name="style-group"></a>スタイルグループ

[C26438 NO_GOTO](C26438.md)\
避ける `goto` 。 C++ Core Guidelines の「 [76](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es76-avoid-goto)」を参照してください。

## <a name="function-group"></a>関数グループ

[C26439 SPECIAL_NOEXCEPT](C26439.md)\
この種の関数は、をスローしない場合があります。 宣言 **`noexcept`** します。 「 [C++ Core Guidelines f.](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f6-if-your-function-may-not-throw-declare-it-noexcept)」を参照してください。

[C26440 DECLARE_NOEXCEPT](C26440.md)\
関数 '*symbol*' は宣言でき **`noexcept`** ます。 「 [C++ Core Guidelines f.](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f6-if-your-function-may-not-throw-declare-it-noexcept)」を参照してください。

[C26447 DONT_THROW_IN_NOEXCEPT](c26447.md)\
関数が宣言されてい **`noexcept`** ますが、例外をスローする可能性がある関数を呼び出しています。
C++ Core Guidelines を参照してください: [F. 6: 関数がスローされない場合は、それを noexcept と宣言](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f6-if-your-function-may-not-throw-declare-it-noexcept)します。

## <a name="concurrency-group"></a>同時実行グループ

[C26441 NO_UNNAMED_GUARDS](C26441.md)\
ガードオブジェクトの名前はにする必要があります。 「 [C++ Core Guidelines cp](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#cp44-remember-to-name-your-lock_guards-and-unique_locks)」を参照してください。

## <a name="const-group"></a>CONST グループ

[C26460 USE_CONST_REFERENCE_ARGUMENTS](c26460.md)\
関数 '*function*' の参照引数 '*argument*' はとしてマークでき `const` ます。 [C++ Core Guidelines con](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rconst-ref)を参照してください。

[C26461 USE_CONST_POINTER_ARGUMENTS](c26461.md): \
関数 '*function*' のポインター引数 '*argument*' は、へのポインターとしてマークでき `const` ます。 [C++ Core Guidelines con](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rconst-ref)を参照してください。

[C26462 USE_CONST_POINTER_FOR_VARIABLE](c26462.md)\
'*Variable*' によってポイントされている値は、1回だけ割り当てられます。へのポインターとしてマークして `const` ください。 [C++ Core Guidelines con](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction)を参照してください。

[C26463 USE_CONST_FOR_ELEMENTS](c26463.md)\
配列 '*array*' の要素は1回だけ割り当てられ `const` ます。マーク要素です。 [C++ Core Guidelines con](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction)を参照してください。

[C26464 USE_CONST_POINTER_FOR_ELEMENTS](c26464.md)\
配列 '*array*' の要素によってポイントされる値は、1回だけ割り当てられます。要素をへのポインターとしてマークし `const` ます。 [C++ Core Guidelines con](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction)を参照してください。

[C26496 USE_CONST_FOR_VARIABLE](c26496.md)\
変数 '*variable*' が割り当てられるのは1回だけです。としてマークして `const` ください。 [C++ Core Guidelines con](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction)を参照してください。

[C26497 USE_CONSTEXPR_FOR_FUNCTION](c26497.md)\
この関数*関数*は、 `constexpr` コンパイル時の評価が必要な場合にマークすることができます。 [C++ Core Guidelines F. 4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rf-constexpr)を参照してください。

[C26498 USE_CONSTEXPR_FOR_FUNCTIONCALL](c26498.md)\
この関数呼び出し*関数*は `constexpr` 、コンパイル時の評価が必要な場合にを使用できます。 [C++ Core Guidelines con](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rconst-constexpr)を参照してください。

## <a name="type-group"></a>型グループ

[C26437 DONT_SLICE](C26437.md)\
スライスしないでください。 「 [C++ CORE GUIDELINES ES](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es63-dont-slice)」を参照してください。

[C26465 NO_CONST_CAST_UNNECESSARY](c26465.md)\
を使用せず `const_cast` にキャスト `const` してください。 `const_cast`は必要ありません。この変換では、変動性または揮発性が削除されていません。 C++ Core Guidelines 「」を参照してください[。 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-constcast).

[C26466 NO_STATIC_DOWNCAST_POLYMORPHIC](c26466.md)\
Downcasts は使用しないで `static_cast` ください。 ポリモーフィックな型からのキャストでは、dynamic_cast を使用する必要があります。 [C++ Core Guidelines の種類を参照してください。 2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-downcast).

[C26471 NO_REINTERPRET_CAST_FROM_VOID_PTR](c26471.md)\
使用しないで `reinterpret_cast` ください。 Void * からのキャストでは、を使用でき `static_cast` ます。 [C++ Core Guidelines の種類を](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast)参照してください。 1.

[C26472 NO_CASTS_FOR_ARITHMETIC_CONVERSION](C26472.md)\
算術変換にはを使用しないで `static_cast` ください。 中かっこ初期化、gsl:: narrow_cast、または gsl:: ナローを使用します。 [C++ Core Guidelines の種類を](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast)参照してください。 1.

[C26473 NO_IDENTITY_CAST](C26473.md)\
変換元の型と変換先の型が同じであるポインター型間ではキャストしないでください。 [C++ Core Guidelines の種類を](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast)参照してください。 1.

[C26474 NO_IMPLICIT_CAST](C26474.md)\
変換が暗黙的である可能性がある場合は、ポインター型の間でキャストしないでください。 [C++ Core Guidelines の種類を](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast)参照してください。 1.

[C26475 NO_FUNCTION_STYLE_CASTS](C26475.md)\
関数スタイルの C キャストは使用しないでください。 [C++ CORE GUIDELINES ES](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es49-if-you-must-use-a-cast-use-a-named-cast)を参照してください。

[C26490 NO_REINTERPRET_CAST](c26490.md)\
使用しないで `reinterpret_cast` ください。 [C++ Core Guidelines の種類を](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type)参照してください。 1.

[C26491 NO_STATIC_DOWNCAST](c26490.md)\
Downcasts は使用しないで `static_cast` ください。 [C++ Core Guidelines の種類を参照してください。 2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).

[C26492 NO_CONST_CAST](c26492.md)\
を使用せず `const_cast` にキャスト `const` してください。 C++ Core Guidelines 「」を参照してください[。 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).

[C26493 NO_CSTYLE_CAST](c26493.md)\
C スタイルのキャストは使用しないでください。 「 [C++ Core Guidelines 種類 4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type)」を参照してください。

[C26494 VAR_USE_BEFORE_INIT](c26494.md)\
変数 '*variable*' は初期化されていません。 常にオブジェクトを初期化します。 「 [C++ Core Guidelines タイプ 5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type)」を参照してください。

[C26495 MEMBER_UNINIT](c26495.md)\
変数 '*variable*' は初期化されていません。 常にメンバー変数を初期化します。 「 [C++ Core Guidelines の種類」を](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type)参照してください。

## <a name="bounds-group"></a>境界グループ

[C26446 USE_GSL_AT](c26446.md)\
Unchecked 添字演算子の代わりにを使用することをお勧め `gsl::at()` します。 「 [C++ Core Guidelines: bounds. 4: 標準ライブラリの関数と、境界がチェックされない型を使用しない](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#probounds-bounds-safety-profile)」を参照してください。

[C26481 NO_POINTER_ARITHMETIC](C26481.md)\
ポインター演算は使用しないでください。 代わりに span を使用します。 「 [C++ Core Guidelines の境界」を](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)参照してください。

[C26482 NO_DYNAMIC_ARRAY_INDEXING](c26482.md)\
定数式を使用して配列にインデックスを作成するだけです。 [C++ Core Guidelines の境界を参照してください。 2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)

[C26483 STATIC_INDEX_OUT_OF_RANGE](c26483.md)\
値の*値*が、変数 '*variable*' の境界 (0、*バインド*) の範囲外です。 配列にインデックスを作成するには、配列の範囲内にある定数式を使用します。 [C++ Core Guidelines の境界を参照してください。 2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)

[C26485 NO_ARRAY_TO_POINTER_DECAY](C26485.md)\
式 '*expr*': 配列からポインターが減衰されていません。 [C++ Core Guidelines の境界を参照してください。 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)

## <a name="gsl-group"></a>GSL グループ

[C26445 NO_SPAN_REF](c26445.md)\
またはへの参照は、 `gsl::span` `std::string_view` 有効期間の問題を示している可能性があります。
[C++ Core Guidelines 「GSL. view: Views」を](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#gslview-views)参照してください。

[C26446 USE_GSL_AT](c26446.md)\
Unchecked 添字演算子の代わりにを使用することをお勧め `gsl::at()` します。 「 [C++ Core Guidelines: bounds. 4: 標準ライブラリの関数と、境界がチェックされない型を使用しない](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#probounds-bounds-safety-profile)」を参照してください。

[C26448 USE_GSL_FINALLY](c26448.md)\
`gsl::finally`最後のアクションが意図されている場合は、の使用を検討してください。 「 [C++ Core Guidelines: GSL. util: Utilities](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-utilities)」を参照してください。

[C26449 NO_SPAN_FROM_TEMPORARY](c26449.md)\
`gsl::span`または一時 `std::string_view` から作成された場合、一時が無効になると無効になります。 「 [C++ Core Guidelines: GSL. view: Views](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#gslview-views)」を参照してください。

## <a name="deprecated-warnings"></a>非推奨の警告

次の警告は、コアガイドラインチェッカーの早期実験用規則セットに含まれていますが、現在は非推奨とされており、無視しても安全です。 警告は、上記の一覧の警告によって置き換えられます。

- 26412 DEREF_INVALID_POINTER
- 26413 DEREF_NULLPTR
- 26420 ASSIGN_NONOWNER_TO_EXPLICIT_OWNER
- 26421 ASSIGN_VALID_OWNER
- 26422 VALID_OWNER_LEAVING_SCOPE
- 26423 ALLOCATION_NOT_ASSIGNED_TO_OWNER
- 26424 VALID_ALLOCATION_LEAVING_SCOPE
- 26425 ASSIGNING_TO_STATIC
- 26499 NO_LIFETIME_TRACKING

## <a name="see-also"></a>関連項目

[C++ Core Guidelines チェッカーの使用](using-the-cpp-core-guidelines-checkers.md)
