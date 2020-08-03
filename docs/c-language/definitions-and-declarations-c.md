---
title: 定義と宣言 (C)
ms.date: 11/04/2016
helpviewer_keywords:
- export functions
ms.assetid: d150395a-89d4-4298-9ac4-08f84fe1261c
ms.openlocfilehash: 0e39832f942eb1473be913112fde1d37ddf05674
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226367"
---
# <a name="definitions-and-declarations-c"></a>定義と宣言 (C)

**Microsoft 固有の仕様**

DLL インターフェイスでは、システム内のプログラムによってエクスポートされることがわかっているすべての項目 (関数とデータ)、つまり、 **`dllimport`** または `dllexport` として宣言されたすべての項目が参照されます。 DLL インターフェイスに含まれるすべての宣言では、 **`dllimport`** または `dllexport` の属性を指定する必要があります。 ただし、定義で指定できるのは `dllexport` 属性のみです。 たとえば、次の関数定義はコンパイラ エラーになります。

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

DllImport int func()    /* Error; dllimport prohibited in */
                        /* definition. */
{
   return 1;
}
```

次のコードでも、エラーが生成します。

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

DllImport int i = 10;      /* Error; this is a definition. */
```

ただし、次に示す構文は、正しい構文です。

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

DllExport int i = 10;      /* Okay: this is an export definition. */
```

`dllexport` の使用は定義を意味するのに対し、 **`dllimport`** は宣言を意味します。 宣言を強制するには、`dllexport` と共に **`extern`** キーワードを使用する必要があります。このようにしない場合、暗黙の定義になります。

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

extern DllImport int k;   /* These are correct and imply */
Dllimport int j;          /* a declaration. */
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[DLL インポートおよびエクスポート関数](../c-language/dll-import-and-export-functions.md)
