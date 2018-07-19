---
title: GetProcAddress |Microsoft ドキュメント
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
ms.openlocfilehash: cec73a7d7aa212c6f53bc2654db6fe40ff96472a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367967"
---
# <a name="getprocaddress"></a>GetProcAddress
プロセスが明示的にリンクする DLL の呼び出しに[GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212) DLL でエクスポートされた関数のアドレスを取得します。 返された関数ポインターを使って、DLL 関数を呼び出します。 **GetProcAddress** DLL モジュール ハンドルをパラメーターとして受け取る (いずれかによって返される**LoadLibrary**、 `AfxLoadLibrary`、または**GetModuleHandle**) と関数の名前呼び出し、関数のエクスポート序数。  
  
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
  
 呼び出し時に関数を指定する方法**GetProcAddress** DLL のビルド方法によって異なります。  
  
 モジュール定義 (.def) ファイルでは、リンク先の DLL が組み込まれている場合、および内の関数に序数が表示されている場合のみ、エクスポート序数を取得できます、**エクスポート**DLL の .def ファイルのセクションです。 呼び出す**GetProcAddress**とエクスポート序数を関数名ではなくが、エクスポート序数果たすエクスポート テーブルの索引の役割を DLL のため、DLL にエクスポートされた関数の多くがある場合に若干速くなります。 エクスポート序数を使って**GetProcAddress** DLL のエクスポート テーブル内の関数名を指定した名前を比較するのではなく、直接関数を見つけることができます。 ただし、呼び出す必要があります**GetProcAddress**割り当てられている序数 .def ファイルにエクスポートされた関数に制御がある場合にのみエクスポート序数を使っています。  
  
## <a name="what-do-you-want-to-do"></a>実行する操作  
  
-   [DLL を暗黙的にリンクする方法](../build/linking-an-executable-to-a-dll.md#linking-implicitly)  
  
-   [リンク方式を使い分け](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [LoadLibrary と AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [FreeLibrary](http://msdn.microsoft.com/library/windows/desktop/ms683152)  
  
-   [DEF ファイルを使った DLL からのエクスポート](../build/exporting-from-a-dll-using-def-files.md)  
  
## <a name="see-also"></a>関連項目  
 [Visual C++ の DLL](../build/dlls-in-visual-cpp.md)