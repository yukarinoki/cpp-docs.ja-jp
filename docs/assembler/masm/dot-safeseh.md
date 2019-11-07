---
title: .SAFESEH
ms.date: 11/05/2019
f1_keywords:
- .SAFESEH
helpviewer_keywords:
- registering functions as exception handlers
- SAFESEH directive
- .SAFESEH directive
ms.assetid: 6eaac8c4-c46f-47ae-8a66-f5cfeb267e43
ms.openlocfilehash: 4577bd5d76949dfb777a359c80d91814f1c45fe2
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "73703949"
---
# <a name="safeseh-32-bit-masm"></a>.SAFESEH (32 ビット MASM)

関数を構造化例外ハンドラーとして登録します。 (32 ビット MASM のみ。)

## <a name="syntax"></a>構文

> .SAFESEH 識別子

## <a name="remarks"></a>Remarks

*識別子*は、ローカルに定義された[Proc](../../assembler/masm/proc.md)または[extrn](../../assembler/masm/extrn.md) proc の id である必要があります。 [ラベル](../../assembler/masm/label-masm.md)は使用できません。 、.SAFESEH ディレクティブには、 [/safeseh](../../assembler/masm/ml-and-ml64-command-line-reference.md) ml .exe コマンドラインオプションが必要です。

構造化例外ハンドラーの詳細については、「 [/safeseh](../../build/reference/safeseh-image-has-safe-exception-handlers.md)」を参照してください。

たとえば、安全な例外ハンドラーを登録するには、次のように新しい MASM ファイルを作成し、/safeseh でアセンブルして、リンクオブジェクトに追加します。

```asm
.386
.model  flat
MyHandler   proto
.safeseh    MyHandler
end
```

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>