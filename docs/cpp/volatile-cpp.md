---
title: volatile (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- volatile_cpp
dev_langs:
- C++
helpviewer_keywords:
- interrupt handlers and volatile keyword [C++]
- volatile keyword [C++]
- volatile objects
- objects [C++], volatile
ms.assetid: 81db4a85-ed5a-4a2c-9a53-5d07a771d2de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 295654586a3fe251526a4764d54f80f3a70c7014
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32423959"
---
# <a name="volatile-c"></a>volatile (C++)
オブジェクトをハードウェアがプログラム内で変更できることを宣言するために使用できる型修飾子です。  
  
## <a name="syntax"></a>構文  
  
```  
  
volatile declarator ;  
```  
  
## <a name="remarks"></a>コメント  
 使用することができます、 [/volatile](../build/reference/volatile-volatile-keyword-interpretation.md)コンパイラ スイッチをこのキーワードをコンパイラが解釈する方法を変更します。  
  
 Visual Studio は、ターゲット アーキテクチャに応じて、`volatile` キーワードの解釈を変えます。 Arm、ない場合は **/volatile**コンパイラ オプションを指定すると、コンパイラは、実行として **/volatile:iso**が指定されています。 いない場合、ARM 以外のアーキテクチャの **/volatile**コンパイラ オプションを指定すると、コンパイラは、実行として **/volatile:ms**が指定されましたそのため、アーキテクチャお強く ARM 以外の場合。指定することをお勧め **/volatile:iso**、およびスレッド間で共有されるメモリを扱うときに、明示的な同期プリミティブとコンパイラ組み込み関数を使用します。  
  
 `volatile` 修飾子を使用すると、割り込みハンドラーのような非同期プロセスによって使用されるメモリ位置へのアクセスを提供することができます。  
  
 ときに`volatile`も持っている変数で使用される、 [_ _restrict](../cpp/extension-restrict.md)キーワード、`volatile`が優先されます。  
  
 `struct` メンバーが `volatile` としてマークされている場合、`volatile` は構造体全体に反映されます。 構造体に、1 つの命令を使用して現在のアーキテクチャでコピーできる長さがない場合、`volatile` がその構造体で完全に失われることがあります。  
  
 次のいずれかの条件が当てはまる場合、`volatile` キーワードはフィールドに対して効果を持ちません。  
  
-   volatile フィールドの長さが、現在のアーキテクチャで 1 つの命令を使用してコピーできる最大サイズを超えている。  
  
-   入れ子になる可能性がある `struct` のメンバーである場合に、最も外側を囲んでいる `struct` の長さが、現在のアーキテクチャで 1 つの命令を使用してコピーできる最大サイズを超えている。  
  
 プロセッサはキャッシュ不可能なメモリ アクセスの順序を変更しませんが、キャッシュ不可能な変数は、コンパイラがメモリ アクセスの順序を変更しないことを保証するために、`volatile` としてマークする必要があります。  
  
 値がいつでも変更可能であるため、`volatile` として宣言されるオブジェクトは、特定の最適化では使用されません。  システムは、以前の命令で同じオブジェクトの値が要求されていても、常に volatile オブジェクトの現在の値を、要求されたときに読み取ります。  また、オブジェクトの値は、代入時にすぐに書き込まれます。  
  
## <a name="iso-compliant"></a>ISO 準拠 →  
 C# volatile キーワード、慣れてまたはの動作に慣れている場合`volatile`以前のバージョンの Visual C では、対応であるを c++ 11 ISO 標準`volatile`キーワードは異なっており、Visual Studio ではサポートされているときに、 [//volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md)コンパイラ オプションを指定します。 ARM では、このオプションが既定で指定されています。 C++11 ISO 標準コードの `volatile` キーワードは、ハードウェア アクセスにのみ使用してください。スレッド間通信には使用しないでください。 スレッド間通信の場合などのメカニズムを使用して[std::atomic\<T >](../standard-library/atomic.md)から、 [C++ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)です。  
  
## <a name="end-of-iso-compliant"></a>END ISO 準拠  
  
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 ときに、 **/volatile:ms**コンパイラ オプションを使用: ARM 以外のアーキテクチャが対象となる場合、既定では、コンパイラは volatile オブジェクトへの参照の間で順序を維持するために余分なコード生成その他のグローバル オブジェクトへの参照を順序付けです。 特に次の点に注意してください。  
  
-   volatile オブジェクトへの書き込み (volatile 書き込み) は、解放セマンティクスを持っています。つまり、命令シーケンスで volatile オブジェクトへの書き込み前に発生するグローバル オブジェクトまたは静的オブジェクトへの参照は、コンパイルされたバイナリでの volatile 書き込みの前に発生します。  
  
-   volatile オブジェクトの読み取り (volatile 読み取り) は、取得セマンティクスを持っています。つまり、命令シーケンスで volatile メモリの読み取り後に発生するグローバル オブジェクトまたは静的オブジェクトへの参照は、コンパイルされたバイナリでの volatile 読み取りの後に発生します。  
  
 これによって、マルチスレッド アプリケーションでのメモリのロックと解放に volatile オブジェクトを使用できるようになります。  
  
> [!NOTE]
>  によって提供される強化された保証に依存、 **/volatile:ms**コンパイラ オプションを使用すると、コードを移植します。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [キーワード](../cpp/keywords-cpp.md)   
 [const](../cpp/const-cpp.md)   
 [const ポインターと volatile ポインター](../cpp/const-and-volatile-pointers.md)