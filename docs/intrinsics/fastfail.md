---
title: __fastfail |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 9cd32639-e395-4c75-9f3a-ac3ba7f49921
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b59aeb1bd2e7986e173608689b0b1c37a0ef247e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33334367"
---
# <a name="fastfail"></a>__fastfail
**Microsoft 固有の仕様**  
  
 最小限のオーバーヘッドで呼び出し元プロセスを直ちに終了します。  
  
## <a name="syntax"></a>構文  
  
```  
void __fastfail(unsigned int code);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `code`  
 プロセス終了の理由を示す、winnt.h または wdm.h からの `FAST_FAIL_<description>` シンボリック定数。  
  
## <a name="return-value"></a>戻り値  
 `__fastfail` 組み込みには戻り値はありません。  
  
## <a name="remarks"></a>コメント  
 `__fastfail`組み込みのメカニズムを提供する、*失敗を高速*要求: 破損した可能性のあるプロセスを即時プロセス終了を要求する方法です。 重大な障害によってプログラムの状態が破損し、回復できずにスタックしている場合は、通常の例外処理機能では処理できません。 `__fastfail` を使用して、最小限のオーバーヘッドでプロセスを終了します。  
  
 内部的には、`__fastfail` はアーキテクチャ固有のいくつかのメカニズムを使用して実装されています。  
  
|アーキテクチャ|命令|コード引数の場所|  
|------------------|-----------------|-------------------------------|  
|x86|int 0x29|ecx|  
|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|int 0x29|rcx|  
|ARM|Opcode 0xDEFB|r0|  
  
 ファスト フェール要求は単体で使用でき、通常は、実行に必要な命令は 2 つのみとなります。 ファスト フェール要求が実行されると、カーネルが適切なアクションを実行します。 ユーザー モードのコードでは、ファスト フェール イベントが発生したときの命令ポインター自体をまたぐメモリの依存関係はありません。 このため、深刻なメモリの破損がある場合でも、その信頼性が最大化されます。  
  
 `code` 引数 (winnt.h または wdm.h の `FAST_FAIL_<description>` シンボリック定数の 1 つ) は障害条件の種類を示すもので、環境固有の方法でエラー レポートに組み込まれます。  
  
 ユーザー モードのファスト フェール要求は、例外コード 0xC0000409 および 1 つ以上の例外パラメーターを持つ、継続不可能なセカンド チャンス例外として示されます。 最初の例外パラメーターは `code` 値です。 この例外コードは、Windows エラー報告 (WER) とデバッグ インフラストラクチャに対して、プロセスが破損していること、および障害に対応して最小限のプロセス内アクションを実行する必要があることを示しています。 カーネル モードのファスト フェール要求は、専用のバグチェック コード `KERNEL_SECURITY_CHECK_FAILURE` (0x139) を使用して実装されます。 どちらの場合も、プログラムが破損した状態にあると予想されるため、例外ハンドラーは呼び出されません。 デバッガーが存在する場合は、プログラムを終了する前にその状態を確認する機会が与えられます。  
  
 Windows 8 から、ネイティブのファスト フェール メカニズムのサポートが開始されました。 ファスト フェール命令をネイティブでサポートしていない Windows オペレーティング システムでは、通常、ファスト フェール要求はアクセス違反または `UNEXPECTED_KERNEL_MODE_TRAP` バグチェックとして処理されます。 このような場合もやはりプログラムは終了しますが、必ずしも直ちに終了するわけではありません。  
  
 `__fastfail` は、組み込みとしてのみ使用できます。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__fastfail`|x86、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]、ARM|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)