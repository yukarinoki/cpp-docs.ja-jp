---
title: GetProcAddress |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- GetProcAddress
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], GetProcAddress
- ordinal exports [C++]
- GetProcAddress method
ms.assetid: 48d14ae0-47ea-4c5d-96b1-2c158f1a26af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 91fd6b983d648b682cbd60fa6126189e102b9f1c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194360"
---
# <a name="getprocaddress"></a>GetProcAddress
明示的にリンクする DLL の呼び出しプロセス[GetProcAddress](https://msdn.microsoft.com/library/windows/desktop/ms683212) DLL でエクスポートされた関数のアドレスを取得します。 返された関数ポインターを使って、DLL 関数を呼び出します。 **GetProcAddress** DLL モジュール ハンドルをパラメーターとして受け取り (いずれかによって返される**LoadLibrary**、 `AfxLoadLibrary`、または**GetModuleHandle**) と関数のいずれかの名前を受け取ります呼び出し、関数のエクスポート序数。  
  
 DLL 関数の呼び出しにはポインターが使われ、コンパイル時にデータ型はチェックされないため、関数へ渡すパラメーターが正しいことを確認してください。パラメーターが不正な場合、スタック上に割り当てられたメモリ域をオーバーしたり、アクセス違反を起こしたりすることがあります。 型をタイプセーフにする 1 つの方法は、エクスポート関数の関数プロトタイプを見て、関数ポインター用に対応する typedef を作成することです。 例えば:  
  
```  
typedef UINT (CALLBACK* LPFNDLLFUNC1)(DWORD,UINT);  
...  
  
HINSTANCE hDLL;               // Handle to DLL  
LPFNDLLFUNC1 lpfnDllFunc1;    // Function pointer  
DWORD dwParam1;  
UINT  uParam2, uReturnVal;  
  
hDLL = LoadLibrary("MyDLL");  
if (hDLL != NULL)  
{  
   lpfnDllFunc1 = (LPFNDLLFUNC1)GetProcAddress(hDLL,  
                                           "DLLFunc1");  
   if (!lpfnDllFunc1)  
   {  
      // handle the error  
      FreeLibrary(hDLL);  
      return SOME_ERROR_CODE;  
   }  
   else  
   {  
      // call the function  
      uReturnVal = lpfnDllFunc1(dwParam1, uParam2);  
   }  
}  
```  
  
 呼び出すときに関数を指定する方法**GetProcAddress** DLL がどのように構築されたかによって異なります。  
  
 モジュール定義 (.def) ファイルにリンクする DLL が組み込まれている場合、および序数がの関数と表示されている場合のみ、エクスポート序数を取得できます、**エクスポート**DLL の .def ファイルのセクション。 呼び出す**GetProcAddress**とエクスポートは、関数名ではなく、序数がエクスポート序数が dll のインデックス テーブルのエクスポートを配信するため、DLL によってエクスポートされた関数の多くがある場合に若干速くなります。 エクスポート序数**GetProcAddress** DLL のエクスポート テーブル内の関数名を指定した名前を比較するのではなく、直接関数を見つけることができます。 ただし、呼び出す必要があります**GetProcAddress** .def ファイルにエクスポートされた関数への序数の割り当てを制御している場合にのみ、エクスポート序数。  
  
## <a name="what-do-you-want-to-do"></a>実行する操作  
  
-   [DLL と暗黙的にリンクする方法](../build/linking-an-executable-to-a-dll.md#linking-implicitly)  
  
-   [リンク方式の使用](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [LoadLibrary と AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [FreeLibrary](https://msdn.microsoft.com/library/windows/desktop/ms683152)  
  
-   [DEF ファイルを使った DLL からのエクスポート](../build/exporting-from-a-dll-using-def-files.md)  
  
## <a name="see-also"></a>関連項目  
 [Visual C++ の DLL](../build/dlls-in-visual-cpp.md)