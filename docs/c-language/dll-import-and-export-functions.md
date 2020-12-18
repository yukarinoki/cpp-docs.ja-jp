---
description: '詳細情報: DLL インポートおよびエクスポート関数'
title: DLL インポートおよびエクスポート関数
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], importing
- dllimport attribute [C++], storage-class attribute
- DLL exports [C++]
- declaring functions, with dllexport and dllimport
- extended storage-class attributes
- dllexport attribute [C++], storage-class attribute
ms.assetid: 08d164b9-770a-4e14-afeb-c6f21d9e33e4
ms.openlocfilehash: 9f734d4415b473717ad8cd7c94213f1beaff9dc8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213931"
---
# <a name="dll-import-and-export-functions"></a>DLL インポートおよびエクスポート関数

**Microsoft 固有の仕様**

このトピックの最も完全な最新情報は「[dllexport、dllimport](../cpp/dllexport-dllimport.md)」で確認できます。

**`dllimport`** および `dllexport` ストレージクラス修飾子は C 言語への Microsoft 固有の拡張です。 これらの修飾子は、クライアント (実行可能ファイルまたは別の DLL) に DLL のインターフェイスを明示的に定義します。 関数を `dllexport` として宣言すると、モジュール定義 (.DEF) ファイルが不要になります。 また、データとオブジェクトに対して修飾子 **`dllimport`** と `dllexport` を使用することもできます。

**`dllimport`** および `dllexport` ストレージクラス修飾子は、この例に示すように拡張属性構文のキーワード、 **`__declspec`** と共に使用する必要があります。

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

DllExport void func();
DllExport int i = 10;
DllExport int j;
DllExport int n;
```

拡張ストレージ クラス修飾子の構文に関する具体的な情報については、「[拡張ストレージ クラス属性](../c-language/c-extended-storage-class-attributes.md)」を参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[C 関数の定義](../c-language/c-function-definitions.md)
