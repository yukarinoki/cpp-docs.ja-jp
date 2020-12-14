---
description: 詳細については、Delay-Loaded DLL のすべてのインポートの読み込みに関するページを参照してください。
title: 遅延読み込みされた DLL に対するすべてのインポートの読み込み
ms.date: 11/04/2016
helpviewer_keywords:
- __HrLoadAllImportsForDll linker option
ms.assetid: 975fcd97-1a56-4a16-9698-e1a249d2d592
ms.openlocfilehash: 0f1334f30568e4722bd97579145ddcae9851b901
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190923"
---
# <a name="loading-all-imports-for-a-delay-loaded-dll"></a>遅延読み込みされた DLL に対するすべてのインポートの読み込み

Delayhlp で定義されている **__HrLoadAllImportsForDll** 関数は、 [/delayload](delayload-delay-load-import.md) リンカーオプションで指定された DLL からすべてのインポートを読み込むようにリンカーに指示します。

すべてのインポートを読み込むことで、エラー処理をコード内の1か所に配置できます。インポートの実際の呼び出しを囲む例外処理を使用する必要はありません。 また、ヘルパーコードがインポートの読み込みに失敗した結果として、アプリケーションがプロセスを部分的に失敗させる状況を回避します。

**__HrLoadAllImportsForDll** を呼び出すと、フックとエラー処理の動作が変わりません。詳細については [、「エラー処理と通知](error-handling-and-notification.md)」を参照してください。

**__HrLoadAllImportsForDll** に渡される dll 名は、dll 自体の内部に格納されている名前と比較され、大文字と小文字が区別されます。

次の例は、 **__HrLoadAllImportsForDll** を呼び出す方法を示しています。

```
if (FAILED(__HrLoadAllImportsForDll("delay1.dll"))) {
   printf ( "failed on snap load, exiting\n" );
   exit(2);
}
```

## <a name="see-also"></a>関連項目

[リンカーによる Delay-Loaded Dll のサポート](linker-support-for-delay-loaded-dlls.md)
