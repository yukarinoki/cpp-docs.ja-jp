---
title: スレッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- thread_cpp
dev_langs:
- C++
helpviewer_keywords:
- thread local storage (TLS)
- thread __declspec keyword
- TLS (thread local storage), compiler implementation
- __declspec keyword [C++], thread
ms.assetid: 667f2a77-6d1f-4b41-bee8-05e67324fab8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f268dd12ca0eca55cbc91bffe5daccbc23ef4dbe
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37940151"
---
# <a name="thread"></a>スレッド

**Microsoft 固有の仕様**

**スレッド**拡張ストレージ クラス修飾子は、スレッド ローカル変数を宣言するために使用します。 C++ 11 で同等およびそれ以降のノートブックを使用して、 [thread_local](../cpp/storage-classes-cpp.md#thread_local)移植可能なコードのストレージ クラス指定子。 Windows で`thread_local`は実装されて`__declspec(thread)`します。

## <a name="syntax"></a>構文

> **__declspec( thread )** *declarator*  

## <a name="remarks"></a>Remarks

スレッド ローカル ストレージ (TLS) は、特定のマルチスレッド プロセスの各スレッドが、スレッド固有のデータを格納するための場所を割り当てる機能です。 標準のマルチスレッド プログラムでは、データは特定のプロセスのすべてのスレッド間で共有されますが、スレッド ローカル ストレージはスレッドごとのデータを割り当てるための機能です。 スレッドの詳細については、次を参照してください。[マルチ スレッド](../parallel/multithreading-support-for-older-code-visual-cpp.md)します。

スレッド ローカル変数の宣言を使用する必要があります[拡張属性構文](../cpp/declspec.md)と **_ _declspec**キーワード、**スレッド**キーワード。 たとえば、次に示すコードは、整数型のスレッド ローカル変数を宣言して特定の値に初期化します。

```cpp
__declspec( thread ) int tls_i = 1;
```

スレッド ローカル変数を動的に読み込まれるライブラリで使用する場合は、スレッド ローカル変数を正しく初期化されませんを引き起こす可能性のある要因を意識する必要があります。

1. (コンス トラクターを含む) が関数呼び出しで、変数が初期化されると、バイナリまたは DLL が読み込まれた後に開始されたスレッドのスレッド、プロセスに読み込むバイナリまたは DLL の原因となったに、この関数が呼び出すのみ。 DLL が読み込まれるときに既に実行されているその他のスレッドの初期化関数は呼び出されません。 動的な初期化は、決して、スレッドの開始時に、DLL がプロセスに含まれていない場合にメッセージを取得の DLL_THREAD_ATTACH、DllMain 呼び出しが、DLL で発生します。

1. 定数値を持つ静的に初期化されるスレッド ローカル変数は、すべてのスレッドでは正しく初期化一般にされます。 ただし、2017 年 12 月の時点で問題がある既知の準拠 constexpr 変数が表示されるため、Microsoft Visual C コンパイラでの静的な初期化ではなく動的です。

   注: 両方の問題の将来のコンパイラの更新プログラムで修正する必要があります。

さらに、スレッド ローカル オブジェクトと変数を宣言するときに、次のガイドラインを確認する必要があります。

- 適用することができます、**スレッド**属性のみをクラスとデータの宣言と定義されます。**スレッド**関数宣言または定義では使用できません。

- 指定することができます、**スレッド**静的ストレージ存続期間のデータ項目にのみ属性。 これには、グローバルなデータ オブジェクトが含まれます (どちらも**静的**と**extern**)、ローカルな静的オブジェクト、およびクラスの静的データ メンバー。 使用して自動データ オブジェクトを宣言することはできません、**スレッド**属性。

- 使用する必要があります、**スレッド**宣言と、スレッド ローカル オブジェクトの定義の属性宣言と定義が同じファイルまたは別のファイルで発生するかどうか。

- 使用することはできません、**スレッド**型修飾子として属性。

- オブジェクトの宣言を使用するため、**スレッド**属性は許可されて、これら 2 つの例は意味的に同等です。

    ```cpp
    // declspec_thread_2.cpp
    // compile with: /LD
    __declspec( thread ) class B {
    public:
       int data;
    } BObject;   // BObject declared thread local.

    class B2 {
    public:
       int data;
    };
    __declspec( thread ) B2 BObject2;   // BObject2 declared thread local.
    ```

- 標準 C では、自分自身への参照を含む式でオブジェクトや変数を初期化できます。ただし、この場合のオブジェクトは、非静的なものに限られます。 C++ では、通常、自分自身への参照を含む式でこのようにオブジェクトを動的に初期化できますが、この種の初期化はスレッド ローカル オブジェクトでは許可されません。 例えば:

   ```cpp
   // declspec_thread_3.cpp
   // compile with: /LD
   #define Thread __declspec( thread )
   int j = j;   // Okay in C++; C error
   Thread int tls_i = sizeof( tls_i );   // Okay in C and C++
   ```

   なお、 **sizeof**初期化されるオブジェクトを含む式自体への参照を構成しないと C および C++ では許可します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__declspec](../cpp/declspec.md)  
[キーワード](../cpp/keywords-cpp.md)  
[スレッド ローカル ストレージ (TLS: Thread Local Storage)](../parallel/thread-local-storage-tls.md)  
