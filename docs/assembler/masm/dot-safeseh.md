---
title: .SAFESEH
ms.date: 08/30/2018
f1_keywords:
- .SAFESEH
helpviewer_keywords:
- registering functions as exception handlers
- SAFESEH directive
- .SAFESEH directive
ms.assetid: 6eaac8c4-c46f-47ae-8a66-f5cfeb267e43
ms.openlocfilehash: adfb9106095de3d15bafb67172b001d0f4597418
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649853"
---
# <a name="safeseh"></a>.SAFESEH

構造化例外ハンドラーとして関数を登録します。

## <a name="syntax"></a>構文

> .SAFESEH 識別子

## <a name="remarks"></a>Remarks

*識別子*の ID をローカルで定義されている必要があります[PROC](../../assembler/masm/proc.md)または[EXTRN](../../assembler/masm/extrn.md)プロシージャ A[ラベル](../../assembler/masm/label-masm.md)は許可されていません。 します。SAFESEH ディレクティブに必要な[/safeseh](../../assembler/masm/ml-and-ml64-command-line-reference.md) ml.exe コマンド ライン オプション。

構造化例外ハンドラーの詳細については、次を参照してください。 [/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md)します。

など安全な例外ハンドラーを登録する (次のように) 新しい MASM ファイルを作成、/safeseh でアセンブリおよびリンク オブジェクトに追加します。

```asm
.386
.model  flat
MyHandler   proto
.safeseh    MyHandler
end
```

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>