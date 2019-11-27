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
ms.openlocfilehash: df9798800da293e5e0b4f545a8442380b7ff9408
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397997"
---
# <a name="safeseh-32-bit-masm"></a>.SAFESEH (32 ビット MASM)

関数を構造化例外ハンドラーとして登録します。 (32 ビット MASM のみ。)

## <a name="syntax"></a>構文

> **.SAFESEH** *識別子*

## <a name="remarks"></a>コメント

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

## <a name="see-also"></a>参照

[ディレクティブリファレンス](directives-reference.md)
