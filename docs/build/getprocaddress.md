---
description: '詳細情報: GetProcAddress'
title: GetProcAddress
ms.date: 11/04/2016
f1_keywords:
- GetProcAddress
helpviewer_keywords:
- DLLs [C++], GetProcAddress
- ordinal exports [C++]
- GetProcAddress method
ms.assetid: 48d14ae0-47ea-4c5d-96b1-2c158f1a26af
ms.openlocfilehash: 32f0d6d623ea3a4499603a1b76e2c320537820fe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162873"
---
# <a name="getprocaddress"></a>GetProcAddress

プロセスに DLL を明示的にリンクする場合は、[GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) を呼び出して、DLL 内のエクスポート関数のアドレスを取得します。 返された関数ポインターを使って、DLL 関数を呼び出します。 **GetProcAddress** のパラメーターには、**LoadLibrary**、`AfxLoadLibrary`、または **GetModuleHandle** のいずかによって返された DLL モジュール ハンドルと、呼び出す関数の名前またはエクスポート序数を渡します。

DLL 関数の呼び出しにはポインターが使われ、コンパイル時にデータ型はチェックされないため、関数へ渡すパラメーターが正しいことを確認してください。パラメーターが不正な場合、スタック上に割り当てられたメモリ域をオーバーしたり、アクセス違反を起こしたりすることがあります。 型をタイプセーフにする 1 つの方法は、エクスポート関数の関数プロトタイプを見て、関数ポインター用に対応する typedef を作成することです。 次に例を示します。

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

**GetProcAddress** の呼び出し時に関数を指定する方法は、ビルドされた DLL の種類によって異なります。

エクスポート序数を使用できるのは、リンクする DLL がモジュール定義ファイル (.def) を使ってビルドされたものであり、その DLL の .def ファイルの **EXPORTS** セクション内の関数に序数が付けられている場合だけです。 関数名ではなくエクスポート序数を使って **GetProcAddress** を呼び出すと、DLL にエクスポート関数が多数含まれる場合は、少し高速になります。エクスポート序数が DLL のエクスポート テーブルの索引の役割を果たすからです。 指定された名前を DLL のエクスポート テーブル内の関数名と比較するのではなく、エクスポート序数を使うと、**GetProcAddress** ではその関数をすぐに発見できます。 ただし、エクスポート序数を使って **GetProcAddress** を呼び出すには、.def ファイル内でエクスポート関数に対して割り当てられている序数を知っている必要があります。

## <a name="what-do-you-want-to-do"></a>実行する操作

- [実行可能ファイルと DLL のリンク](linking-an-executable-to-a-dll.md#linking-implicitly)

- [実行可能ファイルと DLL のリンク](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [LoadLibrary と AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)

- [FreeLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-freelibrary)

- [DEF ファイルを使った DLL からのエクスポート](exporting-from-a-dll-using-def-files.md)

## <a name="see-also"></a>関連項目

[Visual Studio での C/C++ Dll の作成](dlls-in-visual-cpp.md)
