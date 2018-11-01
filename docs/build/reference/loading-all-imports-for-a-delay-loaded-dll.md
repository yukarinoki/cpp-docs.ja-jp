---
title: 遅延読み込みされた DLL に対するすべてのインポートの読み込み
ms.date: 11/04/2016
helpviewer_keywords:
- __HrLoadAllImportsForDll linker option
ms.assetid: 975fcd97-1a56-4a16-9698-e1a249d2d592
ms.openlocfilehash: a9e9df6b0bae49eaf599e56e5d96040afae315e8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536566"
---
# <a name="loading-all-imports-for-a-delay-loaded-dll"></a>遅延読み込みされた DLL に対するすべてのインポートの読み込み

**_ _Hrloadallimportsfordll** delayhlp.cpp で定義されている、関数で指定された DLL からのすべてのインポートを読み込むようにリンカーに指示、 [/delayload](../../build/reference/delayload-delay-load-import.md)リンカー オプション。

すべてのインポートの読み込みを使用すると、コード内の 1 つの場所でエラー処理とインポートの実際の呼び出しを処理する例外を使用する必要はありません。 また、インポートの読み込みに失敗したヘルパー コードの結果としてのプロセスをアプリケーションが部分的に失敗する状況を回避できます。

呼び出す **_ _hrloadallimportsfordll**フック関数とエラーの動作は変わりません処理; を参照してください[エラー処理と通知](../../build/reference/error-handling-and-notification.md)詳細についてはします。

渡される DLL 名 **_ _hrloadallimportsfordll** DLL 自体の内部に格納されている名前と比較され、大文字と小文字を区別します。

次の例は、呼び出す方法を示しています **_ _hrloadallimportsfordll**:。

```
if (FAILED(__HrLoadAllImportsForDll("delay1.dll"))) {
   printf ( "failed on snap load, exiting\n" );
   exit(2);
}
```

## <a name="see-also"></a>関連項目

[リンカーによる DLL の遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)