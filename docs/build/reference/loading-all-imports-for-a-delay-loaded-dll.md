---
description: 遅延読み込みされた DLL のすべてのインポートの読み込みに関する詳細情報
title: 遅延読み込みされた DLL のすべてのインポートを読み込みます
ms.date: 01/19/2021
helpviewer_keywords:
- __HrLoadAllImportsForDll linker option
ms.openlocfilehash: b197c50d3b6b68d77dbfccda99e3c2986c515204
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667213"
---
# <a name="load-all-imports-for-a-delay-loaded-dll"></a>遅延読み込みされた DLL のすべてのインポートを読み込みます

で定義されている関数は、 `__HrLoadAllImportsForDll` *`delayhlp.cpp`* リンカーオプションで指定された DLL からすべてのインポートを読み込むようにリンカーに指示 [`/delayload`](delayload-delay-load-import.md) します。

すべてのインポートを読み込むことで、エラー処理をコード内の1か所に配置できます。インポートの実際の呼び出しを囲む例外処理を使用する必要はありません。 また、ヘルパーコードがインポートの読み込みに失敗した結果として、アプリケーションがプロセスを通じて失敗する状況を回避できます。

を呼び出す `__HrLoadAllImportsForDll` と、フックとエラー処理の動作は変更されません。 詳細については、「 [エラー処理と通知](error-handling-and-notification.md)」を参照してください。

に渡される DLL 名 `__HrLoadAllImportsForDll` は、dll 自体の内部に格納されている名前と比較され、大文字と小文字が区別されます。

次の例は、を呼び出す方法を示してい `__HrLoadAllImportsForDll` ます。

```C
if (FAILED(__HrLoadAllImportsForDll("delay1.dll"))) {
   printf ( "failed on snap load, exiting\n" );
   exit(2);
}
```

## <a name="see-also"></a>こちらもご覧ください

[リンカーによる DLL の遅延読み込み](linker-support-for-delay-loaded-dlls.md)
