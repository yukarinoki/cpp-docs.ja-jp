---
title: 宣言の概要
ms.date: 11/04/2016
ms.assetid: 53a5e9e5-1a33-40b5-9dea-7f669b479329
ms.openlocfilehash: e553f4bdfffcd4bba6a39b2d37af6ba25a3d65d9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170437"
---
# <a name="summary-of-declarations"></a>宣言の概要

*declaration*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*宣言指定子*の*属性-seq*<sub>opt</sub> *init-宣言子リスト*<sub>opt</sub> **;**

*declaration-specifiers*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ストレージクラス指定子*の*宣言指定子*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*型指定子* *の宣言指定子*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*型修飾子*の*宣言指定子*<sub>opt</sub>

*属性-seq* :&nbsp;&nbsp;&nbsp;&nbsp;/\* Microsoft 固有の \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*属性* *の属性-seq*<sub>opt</sub>

*属性*:&nbsp;&nbsp;&nbsp;&nbsp;/\* Microsoft 固有の \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;[__asm](../assembler/inline/asm.md) [__clrcall __stdcall](../cpp/clrcall.md) [__based __fastcall](../cpp/stdcall.md) [__thiscall __cdecl](../cpp/based-grammar.md) [__fastcall](../cpp/fastcall.md) [__inline __vectorcall](../cpp/thiscall.md) [__cdecl](../cpp/cdecl.md) [__inline](../cpp/inline-functions-cpp.md) [__vectorcall](../cpp/vectorcall.md)

*init-declarator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*初期化宣言子リスト* **、** *init 宣言子*

*init-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declarator*<br/>
&nbsp;&nbsp;&nbsp;スカラー初期化=の*初期化子* /\* &nbsp;*宣言***子 \***    /

*storage-class-specifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**auto**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**register**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**static**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**extern**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**typedef**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__declspec (** *拡張宣言-seq* **)**  /\* Microsoft 固有の \*/

*type-specifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**void**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**char**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**short**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**int**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__int8** /\* Microsoft 固有の \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__int16** /\* Microsoft 固有の \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__int32** /\* Microsoft 固有の \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__int64** /\* Microsoft 固有の \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**long**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**float**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**double**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**signed**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**unsigned**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-or-union-specifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*enum-specifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*typedef-name*

*type-qualifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**const**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**volatile**

*declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ポインター*<sub>opt</sub> *ダイレクト宣言子*

*direct-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **(** *宣言子* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*直接宣言子* **[** *定数式の*<sub>選択</sub> **]**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*直接宣言*子 **(** *パラメーター型リスト* **)**  /\* 新しいスタイルの宣言子 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*直接宣言子* **(** *識別子リスト*<sub>opt</sub> **)**  /\* 古い形式の宣言子 \*/

*pointer*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;<strong>\*</strong> *型修飾子の*<sub>選択</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;<strong>\*</strong> *型修飾子リスト*の<sub>opt</sub> *ポインター*

*parameter-type-list*:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/\* パラメーター リスト \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parameter-list*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*パラメーター一覧* **...**

*parameter-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*parameter-declaration*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*パラメーターリスト* **、** *パラメーター宣言*

*type-qualifier-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*type-qualifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*型修飾子-リスト* *型修飾子*

*enum-specifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**列挙型***識別子の*<sub>選択</sub> **{** *enumerator-list* **}**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**列挙型***識別子*

*enumerator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*enumerator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*列挙子-一覧* **、** *列挙子*

*enumerator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*enumeration-constant*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*列挙定数* **=** *定数式*

*enumeration-constant*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*

*struct-or-union-specifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*構造体または共用*体の*識別子の*<sub>opt</sub> **{** *struct-宣言リスト* **}**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*構造体または共用*体の*識別子*

*struct-or-union*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**struct**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**union**

*struct-declaration-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-declaration*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*構造体宣言リスト* *struct-declaration*を宣言する

*struct-declaration*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*指定子-列挙* *体宣言子-list* **;**

*specifier-qualifier-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*型指定*子 *-修飾子リスト*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*型*修飾子*指定子-修飾子リスト*<sub>opt</sub>

*struct-declarator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*構造*体宣言子の構造体宣言子*リスト* **、** *構造*体宣言子

*struct-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*型指定子* *宣言*子<sub>opt</sub> **:** *定数式*

*parameter-declaration*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*宣言指定子*宣言子 /\* 名前付き*宣言子 \** /<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*宣言指定子* *の抽象*<sub> /\*</sub>匿名宣言子 \*/

*identifier-list*: /\* 古い形式の宣言子用 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*識別子-一覧* **、** *識別子*

*abstract-declarator*: /\* Used with anonymous declarators \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*pointer*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ポインター*<sub>opt</sub> -*抽象宣言子*

*direct-abstract-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **(** *抽象宣言子* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*直接抽象宣言子の*<sub>opt</sub> **[** *定数式の*<sub>選択</sub> **]**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*直接抽象宣言子*<sub>opt</sub> **(** *パラメーター型リスト*<sub>opt</sub> **)**

*initializer*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*assignment-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **{** *initializer-list* **}**  /集計の初期化 \* に \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **{** *initializer-list* **,}**

*initializer-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*initializer*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*初期化子リスト* **、** *初期化子*

*type-name*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*指定子-修飾子リスト*の*抽象宣言*の<sub>選択</sub>

*typedef-name*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*

*拡張宣言修飾子-seq*:&nbsp;&nbsp;&nbsp;&nbsp;/\* Microsoft 固有の \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*extended-decl-modifier*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*拡張宣言*によって拡張*宣言修飾子*

*拡張宣言修飾子*:&nbsp;&nbsp;&nbsp;&nbsp;/\* Microsoft 固有 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**thread**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**naked**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllimport**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllexport**

## <a name="see-also"></a>参照

[呼び出し規約](../cpp/calling-conventions.md)<br/>
[句の構造文法](../c-language/phrase-structure-grammar.md)<br/>
[廃止された呼び出し規約](../cpp/obsolete-calling-conventions.md)
