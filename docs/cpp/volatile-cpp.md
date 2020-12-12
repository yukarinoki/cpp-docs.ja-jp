---
description: '詳細情報: volatile (C++)'
title: volatile (C++)
ms.date: 05/07/2019
f1_keywords:
- volatile_cpp
helpviewer_keywords:
- interrupt handlers and volatile keyword [C++]
- volatile keyword [C++]
- volatile objects
- objects [C++], volatile
ms.assetid: 81db4a85-ed5a-4a2c-9a53-5d07a771d2de
ms.openlocfilehash: cb7bda39ded03342b03ed889125992960210b940
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213339"
---
# <a name="volatile-c"></a>volatile (C++)

オブジェクトをハードウェアがプログラム内で変更できることを宣言するために使用できる型修飾子です。

## <a name="syntax"></a>構文

```
volatile declarator ;
```

## <a name="remarks"></a>解説

[/Volatile](../build/reference/volatile-volatile-keyword-interpretation.md)コンパイラスイッチを使用して、コンパイラがこのキーワードを解釈する方法を変更できます。

Visual Studio では、 **`volatile`** ターゲットアーキテクチャによってキーワードが異なる方法で解釈されます。 ARM では、 **/volatile** コンパイラオプションが指定されていない場合、コンパイラは **/volatile: iso** が指定されているかのように実行します。 ARM 以外のアーキテクチャでは、 **/volatile** コンパイラオプションが指定されていない場合、コンパイラは **/volatile: ms** が指定されているかのように実行します。そのため、ARM 以外のアーキテクチャの場合は、 **/volatile: iso** を指定することを強くお勧めします。また、スレッド間で共有されるメモリを扱う場合は、明示的な同期プリミティブとコンパイラ組み込みを使用することをお勧めします。

修飾子を使用して、 **`volatile`** 割り込みハンドラーなどの非同期プロセスによって使用されるメモリ位置へのアクセスを提供できます。

**`volatile`** [__Restrict](../cpp/extension-restrict.md)キーワードも持つ変数でを使用すると、が優先され **`volatile`** ます。

**`struct`** メンバーがとしてマークされている場合 **`volatile`** 、 **`volatile`** は構造体全体に反映されます。 1つの命令を使用して、現在のアーキテクチャでコピーできる長さが構造体にない場合、は **`volatile`** その構造で完全に失われる可能性があります。

**`volatile`** 次の条件のいずれかに該当する場合、キーワードはフィールドに影響しない可能性があります。

- volatile フィールドの長さが、現在のアーキテクチャで 1 つの命令を使用してコピーできる最大サイズを超えている。

- 入れ子になっている可能性があるのメンバーである場合は、最も外側にあるの長さが、 **`struct`** **`struct`** 1 つの命令を使用して現在のアーキテクチャでコピーできる最大サイズを超えています。

プロセッサはキャッシュ不可能なメモリアクセスの順序を変更しませんが、キャッシュされていない変数は、 **`volatile`** コンパイラがメモリアクセスの順序を変更しないことを保証するために、としてマークする必要があります。

として宣言されているオブジェクト **`volatile`** は、値がいつでも変更される可能性があるため、特定の最適化では使用されません。  システムは、以前の命令で同じオブジェクトの値が要求されていても、常に volatile オブジェクトの現在の値を、要求されたときに読み取ります。  また、オブジェクトの値は、代入時にすぐに書き込まれます。

## <a name="iso-compliant"></a>ISO 準拠 →

C# の Volatile キーワードを使い慣れている場合、または以前のバージョンの Microsoft C++ コンパイラ (MSVC) のの動作をよく理解している場合は、 **`volatile`** C++ 11 Iso 標準の **`volatile`** キーワードが異なり、 [/volatile: iso](../build/reference/volatile-volatile-keyword-interpretation.md) コンパイラオプションが指定されている場合は MSVC でサポートされていることに注意してください。 ARM では、このオプションが既定で指定されています。 **`volatile`** C++ 11 ISO 標準コード内のキーワードは、ハードウェアアクセスにのみ使用されます。スレッド間通信には使用しないでください。 スレッド間通信には、 [C++ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)の[std:: atomic \<T> ](../standard-library/atomic.md)などの機構を使用します。

## <a name="end-of-iso-compliant"></a>END ISO 準拠

**Microsoft 固有の仕様**

**/Volatile: ms** コンパイラオプションが使用されている場合 (ARM 以外のアーキテクチャが対象となっている場合、既定では、コンパイラは、他のグローバルオブジェクトへの参照の順序を維持するだけでなく、揮発性オブジェクトへの参照の順序を維持するために追加のコードを生成します。 特に次の点に違いがあります。

- volatile オブジェクトへの書き込み (volatile 書き込み) は、解放セマンティクスを持っています。つまり、命令シーケンスで volatile オブジェクトへの書き込み前に発生するグローバル オブジェクトまたは静的オブジェクトへの参照は、コンパイルされたバイナリでの volatile 書き込みの前に発生します。

- volatile オブジェクトの読み取り (volatile 読み取り) は、取得セマンティクスを持っています。つまり、命令シーケンスで volatile メモリの読み取り後に発生するグローバル オブジェクトまたは静的オブジェクトへの参照は、コンパイルされたバイナリでの volatile 読み取りの後に発生します。

これによって、マルチスレッド アプリケーションでのメモリのロックと解放に volatile オブジェクトを使用できるようになります。

> [!NOTE]
> **/Volatile: ms** コンパイラオプションの使用時に提供される強化された保証に依存する場合、コードは移植できません。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)<br/>
[const](../cpp/const-cpp.md)<br/>
[const ポインターと volatile ポインター](../cpp/const-and-volatile-pointers.md)
