---
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
ms.openlocfilehash: 841b2e1e4ffbec87a170c45be8ad0cd0f831a0ef
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371901"
---
# <a name="volatile-c"></a>volatile (C++)

オブジェクトをハードウェアがプログラム内で変更できることを宣言するために使用できる型修飾子です。

## <a name="syntax"></a>構文

```
volatile declarator ;
```

## <a name="remarks"></a>解説

[/volatile](../build/reference/volatile-volatile-keyword-interpretation.md)コンパイラ スイッチを使用すると、コンパイラがこのキーワードを解釈する方法を変更できます。

ターゲット アーキテクチャによって **、揮発性**キーワードの解釈が異なります。 ARM の場合 **、/volatile**コンパイラ オプションが指定されていない場合、コンパイラは **/volatile:iso**が指定された場合と同様に実行されます。 ARM 以外のアーキテクチャの場合 **、/volatile**コンパイラ オプションが指定されていない場合、コンパイラは **/volatile:ms**が指定されたかのように実行されます。したがって、ARM 以外のアーキテクチャでは、スレッド間で共有されるメモリを処理する場合は **、/volatile:iso**を指定し、明示的な同期プリミティブとコンパイラ組み込みを使用することを強くお勧めします。

**volatile**修飾子を使用すると、割り込みハンドラーなどの非同期プロセスで使用されるメモリの場所へのアクセスを提供できます。

[__restrict](../cpp/extension-restrict.md)キーワードも持つ変数で**volatile**が使用される場合は **、volatile**が優先されます。

**構造体**メンバーが**volatile**としてマークされている場合 **、volatile**は構造体全体に伝達されます。 構造体に、1 つの命令を使用して現在のアーキテクチャ上でコピーできる長さがない場合、**その**構造体で volatile が完全に失われる可能性があります。

次のいずれかの条件に該当する場合 **、volatile**キーワードはフィールドに影響を与える可能性があります。

- volatile フィールドの長さが、現在のアーキテクチャで 1 つの命令を使用してコピーできる最大サイズを超えている。

- 最も外側**の構造体の**長さ (または入れ子になっている**構造体**のメンバーの場合) は、1 つの命令を使用して現在のアーキテクチャにコピーできる最大サイズを超えています。

プロセッサはキャッシュできないメモリ アクセスを並べ替えませんが、コンパイラがメモリ アクセスを並べ替えないことを保証するために、キャッシュできない変数を**volatile**としてマークする必要があります。

**volatile**として宣言されたオブジェクトは、値がいつでも変更される可能性があるため、特定の最適化では使用されません。  システムは、以前の命令で同じオブジェクトの値が要求されていても、常に volatile オブジェクトの現在の値を、要求されたときに読み取ります。  また、オブジェクトの値は、代入時にすぐに書き込まれます。

## <a name="iso-compliant"></a>ISO 準拠 →

C# volatile キーワードに精通している場合、または以前のバージョンの Microsoft C++ コンパイラ (MSVC) で**の揮発性**の動作に慣れている場合は、C++11 ISO 標準**の volatile**キーワードが異なっており[、/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md)コンパイラ オプションが指定されている場合は MSVC でサポートされます。 ARM では、このオプションが既定で指定されています。 C++11 ISO 標準コードの**volatile**キーワードは、ハードウェア アクセスにのみ使用されます。スレッド間通信には使用しないでください。 スレッド間通信では[、c++ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)から[std::atomic\<T>](../standard-library/atomic.md)などのメカニズムを使用します。

## <a name="end-of-iso-compliant"></a>END ISO 準拠

**マイクロソフト固有**

**/volatile:ms**コンパイラ オプションを使用すると (既定では ARM 以外のアーキテクチャが対象指定されている場合)、コンパイラは他のグローバル オブジェクトへの参照への順序を維持するだけでなく、volatile オブジェクトへの参照間で順序を維持するための余分なコードを生成します。 特に次の点に違いがあります。

- volatile オブジェクトへの書き込み (volatile 書き込み) は、解放セマンティクスを持っています。つまり、命令シーケンスで volatile オブジェクトへの書き込み前に発生するグローバル オブジェクトまたは静的オブジェクトへの参照は、コンパイルされたバイナリでの volatile 書き込みの前に発生します。

- volatile オブジェクトの読み取り (volatile 読み取り) は、取得セマンティクスを持っています。つまり、命令シーケンスで volatile メモリの読み取り後に発生するグローバル オブジェクトまたは静的オブジェクトへの参照は、コンパイルされたバイナリでの volatile 読み取りの後に発生します。

これによって、マルチスレッド アプリケーションでのメモリのロックと解放に volatile オブジェクトを使用できるようになります。

> [!NOTE]
> **/volatile:ms**コンパイラ オプションを使用する場合に提供される拡張保証に依存する場合、コードは移植できません。

**エンド マイクロソフト 固有**

## <a name="see-also"></a>関連項目

[Keywords](../cpp/keywords-cpp.md)<br/>
[const](../cpp/const-cpp.md)<br/>
[定数および揮発性のポインタ](../cpp/const-and-volatile-pointers.md)
