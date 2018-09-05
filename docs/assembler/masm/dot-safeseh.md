---
title: .SAFESEH |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .SAFESEH
dev_langs:
- C++
helpviewer_keywords:
- registering functions as exception handlers
- SAFESEH directive
- .SAFESEH directive
ms.assetid: 6eaac8c4-c46f-47ae-8a66-f5cfeb267e43
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d10f3c751fe05c118203bb5eeff6c5cba6ec1c8b
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693169"
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
.model  flat
MyHandler   proto
.safeseh    MyHandler
end
```

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>