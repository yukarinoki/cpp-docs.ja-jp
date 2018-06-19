---
title: dllimport-dllexport に関する規則と制限 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- dllexport attribute [C++], limitations and rules
- dllimport attribute [C++], limitations and rules
- dllexport attribute [C++]
ms.assetid: 274b735f-ab9c-4b07-8d0e-fdb65d664634
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e39c3eb9a45c80ff5e855bd5aacbbef5a9533ef6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32388186"
---
# <a name="rules-and-limitations-for-dllimportdllexport"></a>dllimport/dllexport に関する規則と制限
**Microsoft 固有の仕様**  
  
-   **dllimport** 属性または `dllexport` 属性を指定しないで関数を宣言した場合、その関数は DLL インターフェイスの一部とは見なされません。 したがって、関数の定義は、該当のモジュール内か、同じプログラムの別のモジュール内に存在している必要があります。 関数を DLL インターフェイスに含める場合は、その関数の定義を他のモジュールで `dllexport` として宣言する必要があります。 それ以外の場合、リンカー エラーがクライアントのビルド時に生成されます。  
  
-   プログラムの 1 つのモジュールに、同じ関数の **dllimport** 宣言と `dllexport` 宣言が含まれる場合は、`dllexport` 属性が **dllimport** 属性よりも優先されます。 ただし、コンパイラの警告が生成されます。 例:  
  
    ```  
    #define DllImport   __declspec( dllimport )  
    #define DllExport   __declspec( dllexport )  
  
       DllImport void func1( void );  
       DllExport void func1( void );   /* Warning; dllexport */  
                                       /* takes precedence. */  
  
    ```  
  
-   **dllimport** 属性で宣言されたデータ オブジェクトのアドレスで静的なデータ ポインターを初期化することはできません。 たとえば、次のコードはエラーになります。  
  
    ```  
    #define DllImport   __declspec( dllimport )  
    #define DllExport   __declspec( dllexport )  
  
       DllImport int i;  
       .  
       .  
       .  
       int *pi = &i;                           /* Error */  
  
       void func2()  
       {  
          static int *pi = &i;                   /* Error */  
       }  
  
    ```  
  
-   **dllimport** と宣言された関数のアドレスで静的関数ポインターを初期化すると、ポインターは、関数のアドレスではなく、DLL のインポート サンク (制御を関数に渡すコード スタブ) のアドレスに設定されます。 この代入はエラー メッセージを生成しません。  
  
    ```  
    #define DllImport   __declspec( dllimport )  
    #define DllExport   __declspec( dllexport )  
  
       DllImport void func1( void   
       .  
       .  
       .  
       static void ( *pf )( void ) = &func1;   /* No Error */  
  
       void func2()  
       {  
          static void ( *pf )( void ) = &func1;  /* No Error */  
       }  
  
    ```  
  
-   `dllexport` 属性が含まれたオブジェクト宣言のあるプログラムでは、そのオブジェクトを定義している必要があるため、グローバルまたはローカルの静的関数ポインターを、`dllexport` 関数のアドレスで初期化できます。 同様に、`dllexport` データ オブジェクトのアドレスで、グローバルまたはローカルの静的データ ポインターを初期化できます。 例:  
  
    ```  
    #define DllImport   __declspec( dllimport )  
    #define DllExport   __declspec( dllexport )  
  
       DllImport void func1( void );  
       DllImport int i;  
  
       DllExport void func1( void );  
       DllExport int i;  
       .  
       .  
       .  
       int *pi = &i;                            /* Okay */  
       static void ( *pf )( void ) = &func1;    /* Okay */  
  
       void func2()  
       {  
          static int *pi = i;                     /* Okay */  
          static void ( *pf )( void ) = &func1;   /* Okay */  
       }  
  
    ```  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [DLL インポートおよびエクスポート関数](../c-language/dll-import-and-export-functions.md)