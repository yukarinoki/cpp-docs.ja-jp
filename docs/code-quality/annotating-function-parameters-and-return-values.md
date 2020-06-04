---
title: 関数パラメーターと戻り値に対するア名指定
description: 関数パラメーターおよび戻り値の注釈のリファレンス ガイド。
ms.date: 10/15/2019
ms.topic: conceptual
f1_keywords:
- _Outptr_opt_result_bytebuffer_to_
- _Inout_updates_all_opt_
- _Post_equal_to_
- _Outptr_opt_result_maybenull_
- _Out_writes_bytes_all_
- _Out_writes_all_opt_
- _In_opt_
- _Outptr_
- _Outptr_result_maybenull_
- _Outref_result_bytebuffer_all_maybenull_
- _Inout_updates_opt_z_
- _Inout_updates_z_
- _Out_writes_
- _Out_writes_to_ptr_opt_z_
- _In_reads_to_ptr_opt_
- _Ret_writes_to_maybenull_
- _Outref_result_maybenull_
- _Ret_writes_bytes_
- _Outptr_result_bytebuffer_
- _Out_writes_opt_
- _Inout_updates_bytes_opt_
- _In_z_
- _Inout_updates_to_
- _Ret_maybenull_
- _Ret_writes_bytes_to_
- _Ret_z_
- _COM_Outptr_
- _Ret_maybenull_z_
- _Out_opt_
- _In_reads_opt_z_
- _Outptr_result_bytebuffer_to_
- _Ret_notnull_
- _COM_Outptr_opt_result_maybenull_
- _Inout_updates_to_opt_
- _Inout_updates_
- _Outptr_opt_result_buffer_
- _Outptr_result_buffer_to_
- _Out_writes_to_ptr_opt_
- _Out_writes_bytes_all_opt_
- _Inout_updates_all_
- _Deref_inout_range_
- _Ret_writes_
- _Out_writes_z_
- _Ret_writes_to_
- _Out_writes_to_ptr_z_
- _Out_writes_bytes_to_opt_
- _In_reads_or_z_
- _Inout_updates_bytes_to_
- _In_reads_z_
- _In_opt_z_
- _Outref_result_buffer_maybenull_
- _Ret_range_
- _COM_Outptr_opt_
- _Outptr_opt_result_maybenull_z_
- _In_reads_opt_
- _Inout_
- _Field_range_
- _Ret_writes_z_
- _Out_writes_to_
- _Out_writes_to_ptr_
- _Inout_opt_z_
- _Outref_
- _Deref_out_range_
- _Outref_result_buffer_
- _Outref_result_buffer_to_
- _Outref_result_bytebuffer_to_maybenull_
- _In_reads_bytes_
- _Outptr_opt_result_buffer_to_
- _Outref_result_buffer_all_
- _Out_writes_bytes_to_
- _Result_zeroonfailure_
- _In_reads_bytes_opt_
- _Outref_result_buffer_to_maybenull_
- _Outref_result_bytebuffer_all_
- _Outref_result_buffer_all_maybenull_
- _Ret_writes_maybenull_z_
- _In_range_
- _Inout_updates_bytes_all_opt_
- _Outref_result_bytebuffer_to_
- _Inout_updates_bytes_to_opt_
- _Pre_equal_to_
- _Ret_writes_bytes_maybenull_
- _COM_Outptr_result_maybenull_
- _Ret_writes_maybenull_
- _Out_writes_bytes_
- _Outptr_opt_
- _Out_writes_opt_z_
- _Outref_result_nullonfailure_
- _Outptr_opt_result_z_
- _Inout_opt_
- _Deref_in_range_
- _Outptr_result_z_
- _In_reads_to_ptr_opt_z_
- _Struct_size_bytes_
- _Outptr_result_nullonfailure_
- _In_
- _Inout_updates_bytes_
- _In_reads_to_ptr_z_
- _Ret_writes_bytes_to_maybenull
- _Outptr_opt_result_nullonfailure_
- _In_reads_to_ptr_
- _Outptr_result_buffer_
- _Out_
- _Outref_result_bytebuffer_maybenull_
- _Outptr_result_maybenull_z_
- _In_reads_
- _Inout_updates_opt_
- _Out_writes_to_opt_
- _Outptr_opt_result_bytebuffer_
- _Out_writes_all_
- _Out_range_
- _Inout_updates_bytes_all_
- _Inout_z_
- _Outref_result_bytebuffer_
- _Result_nullonfailure_
- _Ret_null_
- _Scanf_format_string_
- _Scanf_s_format_string_
- _Printf_format_string_
ms.assetid: 82826a3d-0c81-421c-8ffe-4072555dca3a
ms.openlocfilehash: c787dcfb252da1abe47251d66c46689db289cf15
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328009"
---
# <a name="annotating-function-parameters-and-return-values"></a>関数パラメーターと戻り値に対するア名指定

この記事では、単純な関数パラメーター (スカラー、構造体とクラスへのポインター) とほとんどの種類のバッファーに対する注釈の一般的な使用方法について説明します。 この記事では、注釈の一般的な使用パターンも示します。 関数に関連するその他の注釈については、「[関数の動作に注釈を付ける](../code-quality/annotating-function-behavior.md)」を参照してください。

## <a name="pointer-parameters"></a>ポインタパラメータ

次の表の注釈に対して、ポインター パラメーターに注釈が付けられるとき、アナライザーは、ポインターが null の場合にエラーを報告します。 この注釈は、ポインターと、指し示されているデータ項目に適用されます。

### <a name="annotations-and-descriptions"></a>注釈と説明

- `_In_`

     スカラー、構造体、構造体へのポインタ等である入力パラメータにアポイントを付ける。 単純なスカラーで明示的に使用できます。 パラメーターは、前の状態で有効である必要があり、変更されません。

- `_Out_`

     スカラー、構造体、構造体へのポインタ等である出力パラメータにアポイントを付ける。 値を返さないオブジェクト (たとえば、値渡しのスカラーなど) にこの注釈を適用しないでください。 パラメーターは、前の状態で有効である必要はありませんが、後の状態で有効である必要があります。

- `_Inout_`

     関数によって変更されるパラメーターにアナティブします。 これは、前の状態と後の状態の両方で有効である必要がありますが、呼び出しの前後に異なる値を持つものと見なされます。 変更可能な値に適用する必要があります。

- `_In_z_`

     入力として使用される null で終わる文字列へのポインター。 文字列は、前の状態で有効である必要があります。 `PSTR`のバリアントが正しいアノテーションを持っている場合は、この方法が推奨されます。

- `_Inout_z_`

     変更される NULL で終わる文字配列へのポインター。 呼び出しの前後で有効である必要がありますが、値が変更されていると見なされます。 null ターミネータは移動できますが、元の null 終端文字までの要素にのみアクセスできます。

- `_In_reads_(s)`

     `_In_reads_bytes_(s)`

     関数によって読み取られる配列へのポインター。 配列はサイズ`s`要素で、そのすべてが有効である必要があります。

     バリアント`_bytes_`は、要素ではなくバイト単位でサイズを指定します。 このバリアントは、サイズを要素として表現できない場合にのみ使用します。 たとえば、文字列`char`は、同様の`_bytes_`関数を使用する場合にのみバリアントを`wchar_t`使用します。

- `_In_reads_z_(s)`

     NULL で終わる配列へのポインターで、既知のサイズを持つ配列。 null ターミネータまでの要素、または`s`null 終端文字がない場合は、前の状態で有効である必要があります。 サイズがバイト単位でわかっている場合は、`s`要素のサイズでスケールします。

- `_In_reads_or_z_(s)`

     NULL で終わる配列、または既知のサイズを持つ配列へのポインター。 null ターミネータまでの要素、または`s`null 終端文字がない場合は、前の状態で有効である必要があります。 サイズがバイト単位でわかっている場合は、`s`要素のサイズでスケールします。 (家族のために`strn`使用されます。

- `_Out_writes_(s)`

     `_Out_writes_bytes_(s)`

     関数によって書き込まれる`s`要素の配列 (resp. バイト) へのポインター。 配列要素は、前の状態で有効である必要はありませんし、ポストステートで有効な要素の数が指定されていません。 パラメーター型に注釈がある場合は、後の状態で適用されます。 次に例を示します。

     ```cpp
     typedef _Null_terminated_ wchar_t *PWSTR;
     void MyStringCopy(_Out_writes_(size) PWSTR p1, _In_ size_t size, _In_ PWSTR p2);
     ```

     この例では、呼び出し元が`size`要素`p1`のバッファーを提供します。 `MyStringCopy`これらの要素の一部を有効にします。 さらに重要なのは、on`_Null_terminated_`の`PWSTR`アノテーションが`p1`、事後状態でヌル終了することを意味します。 このように、有効な要素の数は依然として明確に定義されていますが、特定の要素数は必要ありません。

     バリアント`_bytes_`は、要素ではなくバイト単位でサイズを指定します。 このバリアントは、サイズを要素として表現できない場合にのみ使用します。 たとえば、文字列`char`は、同様の`_bytes_`関数を使用する場合にのみバリアントを`wchar_t`使用します。

- `_Out_writes_z_(s)`

     `s`要素の配列へのポインター。 要素は、前の状態で有効である必要はありません。 事後状態では、null 終端文字 (存在する必要があります) を通る要素は有効である必要があります。 サイズがバイト単位でわかっている場合は、`s`要素のサイズでスケールします。

- `_Inout_updates_(s)`

     `_Inout_updates_bytes_(s)`

     関数内で読み取りと書き込みが行われる配列へのポインター。 これはサイズ`s`要素で、前の状態と後の状態で有効です。

     バリアント`_bytes_`は、要素ではなくバイト単位でサイズを指定します。 このバリアントは、サイズを要素として表現できない場合にのみ使用します。 たとえば、文字列`char`は、同様の`_bytes_`関数を使用する場合にのみバリアントを`wchar_t`使用します。

- `_Inout_updates_z_(s)`

     null で終わる配列へのポインターで、既知のサイズを持つ配列。 null 終端文字 (存在する必要がある) を介した要素は、前の状態と後の状態の両方で有効である必要があります。 事後状態の値は、前の状態の値とは異なると推測されます。NULL 終端文字の場所を含みます。 サイズがバイト単位でわかっている場合は、`s`要素のサイズでスケールします。

- `_Out_writes_to_(s,c)`

     `_Out_writes_bytes_to_(s,c)`

     `_Out_writes_all_(s)`

     `_Out_writes_bytes_all_(s)`

     `s`要素の配列へのポインター。 要素は、前の状態で有効である必要はありません。 事後状態では、-th 要素までの`c`要素は有効でなければなりません。 この`_bytes_`バリアントは、サイズが要素数ではなくバイト単位でわかっている場合に使用できます。

     次に例を示します。

     ```cpp
     void *memcpy(_Out_writes_bytes_all_(s) char *p1, _In_reads_bytes_(s) char *p2, _In_ int s);
     void *wordcpy(_Out_writes_all_(s) DWORD *p1, _In_reads_(s) DWORD *p2, _In_ int s);
     ```

- `_Inout_updates_to_(s,c)`

     `_Inout_updates_bytes_to_(s,c)`

     関数によって読み取られ、書き込まれる配列へのポインター。 サイズ要素の`s`要素で、そのすべてが前の状態で有効である必要があり`c`、要素は事後状態で有効である必要があります。

     バリアント`_bytes_`は、要素ではなくバイト単位でサイズを指定します。 このバリアントは、サイズを要素として表現できない場合にのみ使用します。 たとえば、文字列`char`は、同様の`_bytes_`関数を使用する場合にのみバリアントを`wchar_t`使用します。

- `_Inout_updates_all_(s)`

     `_Inout_updates_bytes_all_(s)`

     size`s`要素の関数によって読み取りと書き込みが行われる配列へのポインター。 次の値と同等として定義されます。

     `_Inout_updates_to_(_Old_(s), _Old_(s))    _Inout_updates_bytes_to_(_Old_(s), _Old_(s))`

     つまり、バッファー内に存在する`s`、前の状態までのすべての要素は、前の状態と後の状態で有効です。

     バリアント`_bytes_`は、要素ではなくバイト単位でサイズを指定します。 このバリアントは、サイズを要素として表現できない場合にのみ使用します。 たとえば、文字列`char`は、同様の`_bytes_`関数を使用する場合にのみバリアントを`wchar_t`使用します。

- `_In_reads_to_ptr_(p)`

     有効な式である`p - _Curr_`(`p`マイナス`_Curr_`) 配列へのポインター。 前`p`の要素は、前の状態で有効である必要があります。

    次に例を示します。

    ```cpp
    int ReadAllElements(_In_reads_to_ptr_(EndOfArray) const int *Array, const int *EndOfArray);
    ```

- `_In_reads_to_ptr_z_(p)`

     式 (`p - _Curr_``p`マイナス`_Curr_`) が有効な式である NULL で終わる配列へのポインター。 前`p`の要素は、前の状態で有効である必要があります。

- `_Out_writes_to_ptr_(p)`

     有効な式である`p - _Curr_`(`p`マイナス`_Curr_`) 配列へのポインター。 前`p`の要素は、前の状態で有効である必要はありませんし、ポスト状態で有効である必要があります。

- `_Out_writes_to_ptr_z_(p)`

     NULL で終わる配列へのポインタ`p - _Curr_`(つまり、`p`負`_Curr_`の値) が有効な式です。 前`p`の要素は、前の状態で有効である必要はありませんし、ポスト状態で有効である必要があります。

## <a name="optional-pointer-parameters"></a>オプションのポインター・パラメーター

ポインター パラメーターの注釈に`_opt_`が含まれる場合、パラメーターが null である可能性があることを示します。 それ以外の場合、注釈は を含`_opt_`まないバージョンと同じように動作します。 ポインター パラメーターの注釈の`_opt_`バリアントの一覧を次に示します。

||||
|-|-|-|
|`_In_opt_`<br /><br /> `_Out_opt_`<br /><br /> `_Inout_opt_`<br /><br /> `_In_opt_z_`<br /><br /> `_Inout_opt_z_`<br /><br /> `_In_reads_opt_`<br /><br /> `_In_reads_bytes_opt_`<br /><br /> `_In_reads_opt_z_`|`_Out_writes_opt_`<br /><br /> `_Out_writes_opt_z_`<br /><br /> `_Inout_updates_opt_`<br /><br /> `_Inout_updates_bytes_opt_`<br /><br /> `_Inout_updates_opt_z_`<br /><br /> `_Out_writes_to_opt_`<br /><br /> `_Out_writes_bytes_to_opt_`<br /><br /> `_Out_writes_all_opt_`<br /><br /> `_Out_writes_bytes_all_opt_`|`_Inout_updates_to_opt_`<br /><br /> `_Inout_updates_bytes_to_opt_`<br /><br /> `_Inout_updates_all_opt_`<br /><br /> `_Inout_updates_bytes_all_opt_`<br /><br /> `_In_reads_to_ptr_opt_`<br /><br /> `_In_reads_to_ptr_opt_z_`<br /><br /> `_Out_writes_to_ptr_opt_`<br /><br /> `_Out_writes_to_ptr_opt_z_`|

## <a name="output-pointer-parameters"></a>出力ポインタパラメータ

出力ポインター パラメーターでは、パラメーターと指先の位置の NULL 性を明確にするために特別な表記法が必要です。

### <a name="annotations-and-descriptions"></a>注釈と説明

- `_Outptr_`

   パラメーターを null にすることはできませんし、ポストステートでは、ポイント先の場所は null にすることはできませんし、有効である必要があります。

- `_Outptr_opt_`

   パラメーターは null である可能性がありますが、ポストステートでは、ポイント先の場所は null にすることはできません。

- `_Outptr_result_maybenull_`

   パラメーターを null にすることはできませんし、ポストステートでは、ポイント先の場所を null にできます。

- `_Outptr_opt_result_maybenull_`

   パラメーターは null で、ポストステートでは、ポイント先の場所を null にすることができます。

  次の表では、注釈の意味をさらに限定するために、追加の部分文字列がアノテーション名に挿入されます。 さまざまな部分`_z`文字列は、 `_COM_`、 `_buffer_` `_bytebuffer_`、 `_to_`、 、 、 、 です。

> [!IMPORTANT]
> 注釈を付けるインターフェイスが COM の場合は、これらの注釈の COM フォームを使用します。 COM 注釈を他の型インターフェイスと共に使用しないでください。

- `_Outptr_result_z_`

   `_Outptr_opt_result_z_`

   `_Outptr_result_maybenull_z_`

   `_Outptr_opt_result_maybenull_z_`

   返されたポインターには、`_Null_terminated_`注釈があります。

- `_COM_Outptr_`

   `_COM_Outptr_opt_`

   `_COM_Outptr_result_maybenull_`

   `_COM_Outptr_opt_result_maybenull_`

   返されたポインターには COM セマンティクスがあるため、返`_On_failure_`されたポインターが null であるという事後条件が含まれる。

- `_Outptr_result_buffer_(s)`

   `_Outptr_result_bytebuffer_(s)`

   `_Outptr_opt_result_buffer_(s)`

   `_Outptr_opt_result_bytebuffer_(s)`

   返されたポインターは、サイズ`s`の要素またはバイトの有効なバッファーを指します。

- `_Outptr_result_buffer_to_(s, c)`

   `_Outptr_result_bytebuffer_to_(s, c)`

   `_Outptr_opt_result_buffer_to_(s,c)`

   `_Outptr_opt_result_bytebuffer_to_(s,c)`

   返されたポインターは、最初の要素または`s`バイトのバッファーを指し、その`c`バッファーが有効です。

一部のインターフェイス規則では、失敗時に出力パラメータが無効になっていると推測されます。 明示的な COM コードを除き、次の表のフォームが優先されます。 COM コードの場合は、前のセクションに記載されている対応する COM フォームを使用します。

- `_Result_nullonfailure_`

   他の注釈を変更します。 関数が失敗した場合、結果は null に設定されます。

- `_Result_zeroonfailure_`

   他の注釈を変更します。 関数が失敗した場合、結果はゼロに設定されます。

- `_Outptr_result_nullonfailure_`

   返されたポインターは、関数が成功した場合は有効なバッファーを指し、関数が失敗した場合は null を指します。 この注釈は、省略可能でないパラメーター用です。

- `_Outptr_opt_result_nullonfailure_`

   返されたポインターは、関数が成功した場合は有効なバッファーを指し、関数が失敗した場合は null を指します。 この注釈は、省略可能なパラメーターです。

- `_Outref_result_nullonfailure_`

   返されたポインターは、関数が成功した場合は有効なバッファーを指し、関数が失敗した場合は null を指します。 この注釈は参照パラメーター用です。

## <a name="output-reference-parameters"></a>出力参照パラメータ

参照パラメーターの一般的な用途は、出力パラメーターです。 などの`int&`単純な出力参照パラメーターの場合`_Out_`、正しいセマンティクスが提供されます。 ただし、出力値が ポインタの場合など`int *&`、同等のポインター注釈`_Outptr_ int **`は正しいセマンティクスを提供しません。 ポインター型の出力参照パラメーターのセマンティクスを簡潔に表現するには、次の複合アノテーションを使用します。

### <a name="annotations-and-descriptions"></a>注釈と説明

- `_Outref_`

     結果は後の状態で有効である必要があり、null にすることはできません。

- `_Outref_result_maybenull_`

     結果は後の状態で有効である必要がありますが、後の状態では null になる可能性があります。

- `_Outref_result_buffer_(s)`

     結果は後の状態で有効である必要があり、null にすることはできません。 サイズ`s`要素の有効なバッファーへのポイント。

- `_Outref_result_bytebuffer_(s)`

     結果は後の状態で有効である必要があり、null にすることはできません。 サイズのバイト`s`の有効なバッファーへのポイント。

- `_Outref_result_buffer_to_(s, c)`

     結果は後の状態で有効である必要があり、null にすることはできません。 要素の`s`バッファーへのポイントで、最初の要素`c`が有効です。

- `_Outref_result_bytebuffer_to_(s, c)`

     結果は後の状態で有効である必要があり、null にすることはできません。 最初`c`のバイトが`s`有効なバイトのバッファーへのポイント。

- `_Outref_result_buffer_all_(s)`

     結果は後の状態で有効である必要があり、null にすることはできません。 サイズ`s`の有効な要素の有効なバッファーへのポイント。

- `_Outref_result_bytebuffer_all_(s)`

     結果は後の状態で有効である必要があり、null にすることはできません。 有効な要素のバイト`s`の有効なバッファーへのポイント。

- `_Outref_result_buffer_maybenull_(s)`

     結果は後の状態で有効である必要がありますが、後の状態では null になる可能性があります。 サイズ`s`要素の有効なバッファーへのポイント。

- `_Outref_result_bytebuffer_maybenull_(s)`

     結果は後の状態で有効である必要がありますが、後の状態では null になる可能性があります。 サイズのバイト`s`の有効なバッファーへのポイント。

- `_Outref_result_buffer_to_maybenull_(s, c)`

     結果は後の状態で有効である必要がありますが、後の状態では null になる可能性があります。 要素の`s`バッファーへのポイントで、最初の要素`c`が有効です。

- `_Outref_result_bytebuffer_to_maybenull_(s,c)`

     結果は後の状態で有効である必要がありますが、ポスト状態では null になる可能性があります。 最初`c`のバイトが`s`有効なバイトのバッファーへのポイント。

- `_Outref_result_buffer_all_maybenull_(s)`

     結果は後の状態で有効である必要がありますが、ポスト状態では null になる可能性があります。 サイズ`s`の有効な要素の有効なバッファーへのポイント。

- `_Outref_result_bytebuffer_all_maybenull_(s)`

     結果は後の状態で有効である必要がありますが、ポスト状態では null になる可能性があります。 有効な要素のバイト`s`の有効なバッファーへのポイント。

## <a name="return-values"></a>戻り値

関数の戻り値は`_Out_`パラメーターに似ていますが、参照解除のレベルが異なっており、結果へのポインターの概念を考慮する必要はありません。 次の注釈の場合、戻り値は注釈付きオブジェクト (スカラー、構造体へのポインター、またはバッファーへのポインター) です。 これらのアノテーションは、対応する`_Out_`アノテーションと同じセマンティクスを持っています。

|||
|-|-|
|`_Ret_z_`<br /><br /> `_Ret_writes_(s)`<br /><br /> `_Ret_writes_bytes_(s)`<br /><br /> `_Ret_writes_z_(s)`<br /><br /> `_Ret_writes_to_(s,c)`<br /><br /> `_Ret_writes_maybenull_(s)`<br /><br /> `_Ret_writes_to_maybenull_(s)`<br /><br /> `_Ret_writes_maybenull_z_(s)`|`_Ret_maybenull_`<br /><br /> `_Ret_maybenull_z_`<br /><br /> `_Ret_null_`<br /><br /> `_Ret_notnull_`<br /><br /> `_Ret_writes_bytes_to_`<br /><br /> `_Ret_writes_bytes_maybenull_`<br /><br /> `_Ret_writes_bytes_to_maybenull_`|

## <a name="format-string-parameters"></a>書式文字列パラメーター

- `_Printf_format_string_`パラメーターが`printf`式で使用する書式指定文字列であることを示します。

     **例**

    ```cpp
    int MyPrintF(_Printf_format_string_ const wchar_t* format, ...)
    {
           va_list args;
           va_start(args, format);
           int ret = vwprintf(format, args);
           va_end(args);
           return ret;
    }
    ```

- `_Scanf_format_string_`パラメーターが`scanf`式で使用する書式指定文字列であることを示します。

     **例**

    ```cpp
    int MyScanF(_Scanf_format_string_ const wchar_t* format, ...)
    {
           va_list args;
           va_start(args, format);
           int ret = vwscanf(format, args);
           va_end(args);
           return ret;
    }
    ```

- `_Scanf_s_format_string_`パラメーターが`scanf_s`式で使用する書式指定文字列であることを示します。

     **例**

    ```cpp
    int MyScanF_s(_Scanf_s_format_string_ const wchar_t* format, ...)
    {
           va_list args;
           va_start(args, format);
           int ret = vwscanf_s(format, args);
           va_end(args);
           return ret;
    }
    ```

## <a name="other-common-annotations"></a>その他の一般的な注釈

### <a name="annotations-and-descriptions"></a>注釈と説明

- `_In_range_(low, hi)`

     `_Out_range_(low, hi)`

     `_Ret_range_(low, hi)`

     `_Deref_in_range_(low, hi)`

     `_Deref_out_range_(low, hi)`

     `_Deref_inout_range_(low, hi)`

     `_Field_range_(low, hi)`

     パラメーター、フィールド、または結果は、 から から までの`low`範囲`hi`(両端を含む) に含まれます。 `_Satisfies_(_Curr_ >= low && _Curr_ <= hi)`それと同等の、適切な前状態または後状態条件と共に、アコード化されたオブジェクトに適用されます。

    > [!IMPORTANT]
    > 名前には "in" と "out" が含まれています`_In_`が`_Out_`、これらのアノテーションには意味が含まれ、その意味は適用**されません**。

- `_Pre_equal_to_(expr)`

     `_Post_equal_to_(expr)`

     この場合、アナンサ値は`expr`正確です。 `_Satisfies_(_Curr_ == expr)`それと同等の、適切な前状態または後状態条件と共に、アコード化されたオブジェクトに適用されます。

- `_Struct_size_bytes_(size)`

     構造体またはクラスの宣言に適用されます。 この型の有効なオブジェクトが、宣言された型より大きく、バイト数が によって`size`与えられる可能性があることを示します。 次に例を示します。

     `typedef _Struct_size_bytes_(nSize) struct MyStruct {    size_t nSize;    ... };`

     次に、型`pM``MyStruct *`のパラメーターのバッファー・サイズ (バイト) は、次のように取られます。

     `min(pM->nSize, sizeof(MyStruct))`

## <a name="related-resources"></a>関連資料

[コード分析チームのブログ](https://blogs.msdn.microsoft.com/codeanalysis/)

## <a name="see-also"></a>関連項目

- [SAL 注釈を使って C/C++ のコード障害を減らす方法](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
- [SAL について](../code-quality/understanding-sal.md)
- [関数の動作に注釈を付ける](../code-quality/annotating-function-behavior.md)
- [構造体とクラスに注釈を付ける](../code-quality/annotating-structs-and-classes.md)
- [ロック動作に注釈を付ける](../code-quality/annotating-locking-behavior.md)
- [注釈を適用するタイミングと場所の指定](../code-quality/specifying-when-and-where-an-annotation-applies.md)
- [組み込み関数](../code-quality/intrinsic-functions.md)
- [ベスト プラクティスと例](../code-quality/best-practices-and-examples-sal.md)
