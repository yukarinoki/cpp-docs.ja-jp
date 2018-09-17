---
title: 言語固有のハンドラー |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 6503e0cd-2d3a-4330-a925-8bed8c27c2be
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 678f5695523751ebc1ef3c5dba2b63154b21833c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714949"
---
# <a name="language-specific-handler"></a>言語固有のハンドラー

存在する UNW_FLAG_EHANDLER または UNW_FLAG_UHANDLER フラグが設定されるたびに、言語固有のハンドラーの相対アドレスが UNWIND_INFO 内に存在します。 前のセクションで説明した、またはアンワインドの一部として例外ハンドラーの検索の一部として、言語固有のハンドラーが呼び出されます。 次のプロトタイプがあります。

```
typedef EXCEPTION_DISPOSITION (*PEXCEPTION_ROUTINE) (
    IN PEXCEPTION_RECORD ExceptionRecord,
    IN ULONG64 EstablisherFrame,
    IN OUT PCONTEXT ContextRecord,
    IN OUT PDISPATCHER_CONTEXT DispatcherContext
);
```

**ExceptionRecord** Win64 の標準の定義がある例外のレコードへのポインターを提供します。

**EstablisherFrame**のこの関数の固定のスタック割り当てのベース アドレスです。

**ContextRecord** (例外ハンドラーの例) では、例外が発生した時または現在の例外コンテキストへのポインター「アンワインド」(終了ハンドラーの場合) のコンテキスト。

**DispatcherContext**この関数のコンテキストをディスパッチャーを指します。 次の定義があります。

```
typedef struct _DISPATCHER_CONTEXT {
    ULONG64 ControlPc;
    ULONG64 ImageBase;
    PRUNTIME_FUNCTION FunctionEntry;
    ULONG64 EstablisherFrame;
    ULONG64 TargetIp;
    PCONTEXT ContextRecord;
    PEXCEPTION_ROUTINE LanguageHandler;
    PVOID HandlerData;
} DISPATCHER_CONTEXT, *PDISPATCHER_CONTEXT;
```

**ControlPc** RIP のこの関数内の値です。 例外のアドレスまたはアドレスのコントロールを確立する関数のままになります。 これは、コントロールがこの関数内でいくつかの保護されたコンス トラクター内かを判断するために使用する RIP (_ _try ブロックなどの\__try/\__except または\__try/\__finally)。

**ImageBase**イメージ ベース (の読み込みアドレス) の関数のエントリで使用される 32 ビット オフセットに追加して、アンワインド相対アドレスを記録する情報をこの関数を含むモジュールは、します。

**FunctionEntry** RUNTIME_FUNCTION へのポインターを提供しますが、関数を保持するエントリを関数をアンワインド情報イメージ ベースの相対アドレスはこの関数の。

**EstablisherFrame**のこの関数の固定のスタック割り当てのベース アドレスです。

**TargetIp**アンワインドの継続のアドレスを指定する省略可能な命令アドレスを提供します。 場合、このアドレスは無視されます**EstablisherFrame**が指定されていません。

**ContextRecord**システム例外ディスパッチ/アンワインド コードで使用するため、例外コンテキストを指しています。

**LanguageHandler**呼び出されている言語に固有の言語ハンドラー ルーチンを指します。

**HandlerData**この関数の言語固有のハンドラーのデータを指します。

## <a name="see-also"></a>関連項目

[例外処理 (x64)](../build/exception-handling-x64.md)