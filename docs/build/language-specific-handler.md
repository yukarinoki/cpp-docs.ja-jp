---
title: 言語固有のハンドラー |Microsoft ドキュメント
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
ms.openlocfilehash: c6cbfbe6a9b98828a63fb4a092717bfab583e9a2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="language-specific-handler"></a>言語固有のハンドラー
存在する UNW_FLAG_EHANDLER または UNW_FLAG_UHANDLER フラグが設定されるたびに、言語固有のハンドラーの相対アドレスが UNWIND_INFO 内に存在します。 前のセクションで説明した、言語固有のハンドラーは、例外ハンドラーの検索の一部として、またはアンワインドの一部として呼び出されます。 次のプロトタイプがあります。  
  
```  
typedef EXCEPTION_DISPOSITION (*PEXCEPTION_ROUTINE) (  
    IN PEXCEPTION_RECORD ExceptionRecord,  
    IN ULONG64 EstablisherFrame,  
    IN OUT PCONTEXT ContextRecord,  
    IN OUT PDISPATCHER_CONTEXT DispatcherContext  
);  
```  
  
 **ExceptionRecord** Win64、標準の定義を持つ例外レコードへのポインターを提供します。  
  
 **EstablisherFrame**のこの関数の固定のスタック割り当てのベース アドレスです。  
  
 **ContextRecord** (例外ハンドラーの場合) では、例外が発生した時か、または現在の例外コンテキストへのポインター「アンワインド」コンテキスト (終了ハンドラーの場合)。  
  
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
  
 **ControlPc** RIP のこの関数内の値です。 これは、例外のアドレスまたはアドレス コントロールを確立する関数のままです。 これは、この関数内で保護されているか、コンストラクト内のコントロールの判断に使用される RIP (_ _try ブロックなどの\__try/\__except または\__try/\__finally)。  
  
 **ImageBase**基本 (読み込みアドレス) のイメージをこの関数は、関数のエントリで使用されている 32 ビット オフセットに追加して、アンワインド相対アドレスを記録する情報を格納しているモジュールです。  
  
 **FunctionEntry** RUNTIME_FUNCTION へのポインターを提供しますが、関数を保持しているエントリを関数および情報イメージ ベースの相対アドレスはこの関数をアンワインドします。  
  
 **EstablisherFrame**のこの関数の固定のスタック割り当てのベース アドレスです。  
  
 **TargetIp**アンワインドの継続のアドレスを指定する省略可能な命令アドレスを提供します。 場合、このアドレスは無視されます**EstablisherFrame**が指定されていません。  
  
 **ContextRecord**システム例外ディスパッチ/アンワインド コードで使用するため、例外コンテキストを指します。  
  
 **LanguageHandler**呼び出されている言語に固有の言語ハンドラー ルーチンを指します。  
  
 **HandlerData**言語固有のハンドラーのデータをこの関数を指します。  
  
## <a name="see-also"></a>関連項目  
 [例外処理 (x64)](../build/exception-handling-x64.md)