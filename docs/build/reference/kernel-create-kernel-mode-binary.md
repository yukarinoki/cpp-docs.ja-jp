---
title: -カーネル (作成カーネル モード バイナリ) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /kernel
- /kernel-
dev_langs:
- C++
ms.assetid: 6d7fdff0-c3d1-4b78-9367-4da588ce8b05
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbbae275e751287464e4bf1637ee21aff77fb697
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379602"
---
# <a name="kernel-create-kernel-mode-binary"></a>/kernel (カーネル モード バイナリの作成)
Windows カーネルで実行できるバイナリを作成します。  
  
## <a name="syntax"></a>構文  
  
```  
/kernel[-]  
```  
  
## <a name="arguments"></a>引数  
 **/kernel**  
 現在のプロジェクトでコードがコンパイルされ、カーネル モードで実行されるコードに固有の C++ 言語の規則のセットを使用してリンクします。  
  
 **/kernel-**  
 現在のプロジェクトでコードがコンパイルされ、カーネル モードで実行されるコードに固有の C++ 言語の規則を使用せずにリンクされています。  
  
## <a name="remarks"></a>コメント  
 `#pragma` には、このオプションを制御するための相当するものはありません。  
  
 指定する、 **/kernel**オプションは、コンパイラとリンカーがランタイム不安定な状態を回避するための十分な表現力のあることを確認して言語機能がカーネル モードで許可されるかを判別するにはカーネル モード C++ に固有です。 これはカーネル モードで中断を伴う C++ 言語の機能の使用を禁止することでと警告を停止させる可能性が無効にすることはできませんが、C++ 言語の機能を提供することによりします。  
  
 **/Kernel**オプションは、ビルドのコンパイラとリンカーの両方のフェーズに適用され、プロジェクト レベルで設定されています。 渡す、 **/kernel**を結果のバイナリでは、このリンクを作成するを読み込むことは Windows カーネルにコンパイラに示すスイッチです。 コンパイラには、C++ 言語の機能をカーネルと互換性があるサブセットのスペクトルが絞り込まです。  
  
 次の表に、コンパイラの動作の変更時に **/kernel**を指定します。  
  
|動作の種類|**/kernel**動作|  
|-------------------|---------------------------|  
|C++ 例外処理|無効になります。 すべてのインスタンス、`throw`と`try`キーワードは、コンパイラ エラーを生成 (例外の指定を除く`throw()`)。 いいえ **/EH**オプションと互換性が **/kernel**を除く **/EH-** です。|  
|RTTI|無効になります。 すべてのインスタンス、`dynamic_cast`と`typeid`キーワードが、コンパイラ エラーを生成しない限り、`dynamic_cast`は静的に使用します。|  
|`new` および `delete`|明示的に定義する必要があります、`new()`または`delete()`演算子以外の場合は、コンパイラでも、実行時に既定の定義を指定します。|  
  
 呼び出し規約、カスタム、 [/GS](../../build/reference/gs-buffer-security-check.md)ビルド オプション、およびすべての最適化は、使用すると、 **/kernel**オプション。 インライン展開はほとんど受けません **/kernel**、コンパイラによって受け入れられます、同じセマンティクスでします。 確認する場合、`__forceinline`インライン展開の修飾子が受け入れられます、必ずその警告[C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md)特定を知ることが有効になって`__forceinline`関数はインライン関数ではありません。  
  
 コンパイラが渡されたときに、 **/kernel**スイッチ、これには組み込まれて指定されているプリプロセッサ マクロ`_KERNEL_MODE`値を保持して**1**です。 これを使用して、条件付きでかどうかに基づいて、実行時環境では、ユーザー モードまたはカーネル モード コードをコンパイルできます。 たとえば、次のコードでは、クラスは、カーネル モード実行は、コンパイル時にメモリの非ページング セグメントにする必要がありますを指定します。  
  
```cpp  
#ifdef _KERNEL_MODE  
#define NONPAGESECTION __declspec(code_seg("$kerneltext$"))  
#else  
#define NONPAGESECTION  
#endif  
  
class NONPAGESECTION MyNonPagedClass  
{  
   // ...
};  
```  
  
 いくつか次のターゲット アーキテクチャの組み合わせと **/arch**オプションを使用している場合に、エラーを発生 **/kernel**:  
  
-   **/arch: {SSE&#124;SSE2&#124;AVX}** x86 ではサポートされません。 のみ **/arch:IA32**ではサポートされて **/kernel** x86。  
  
-   **/arch:AVX**でサポートされていない **/kernel** x64。  
  
 使用した構築 **/kernel**渡します **/kernel**リンカーにします。 彼女は、リンカーの動作に与える影響です。  
  
-   インクリメンタル リンクは無効です。 追加する場合 **/incremental**リンカーがこの致命的なエラーを生成するコマンド ラインに。  
  
     **リンク: 致命的なエラー LNK1295: '/増分' と互換性がありません '/カーネル ' の指定。'/incremental' なしにリンクします。**  
  
-   各オブジェクト ファイル (または静的ライブラリから含まれるアーカイブ メンバー) を表示するかどうか、でしたがコンパイルされましたを使用して、リンカーが調べ、 **/kernel**オプションでした。 すべてのインスタンスは、この条件を満たす、リンカーが、まだ正常にリンクしますが、次の表に示すように警告を発行する可能性があります。  
  
    ||**/kernel** obj|**/kernel-** obj、MASM obj、または cvtresed|混在 **/kernel**と **/kernel-** objs|  
    |-|----------------------|-----------------------------------------------|-------------------------------------------------|  
    |**リンク/kernel**|[はい]|[はい]|警告 LNK4257 ○ します。|  
    |**リンク**|[はい]|はい|[はい]|  
  
     **/KERNEL; でコンパイルされない LNK4257 リンク オブジェクトイメージは動作しない可能性があります。**  
  
 **/Kernel**オプションおよび **/driver**オプションが独立して動作し、もう一方のどちらに影響します。  
  
### <a name="to-set-the-kernel-compiler-option-in-visual-studio"></a>Visual Studio で/kernel コンパイラ オプションを設定するには  
  
1.  開く、**プロパティ ページ**プロジェクトのダイアログ ボックス。 詳細については、次を参照してください。[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  選択、 **C/C++** フォルダーです。  
  
3.  選択、**コマンドライン**プロパティ ページ。  
  
4.  **追加オプション**ボックスで、追加`/kernel`または`/kernel-`です。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)