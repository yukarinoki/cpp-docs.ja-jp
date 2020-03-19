---
title: コード分析のためのサンプル C++ プロジェクト
ms.date: 11/04/2016
ms.topic: sample
helpviewer_keywords:
- demo sample [Visual Studio ALM]
- code analysis, samples
ms.assetid: 09e1b9f7-5916-4ed6-a001-5c2d7e710682
ms.openlocfilehash: 1966e9cec5825ae37728bbf28c0f21ff4eed62fc
ms.sourcegitcommit: 7bea0420d0e476287641edeb33a9d5689a98cb98
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/17/2020
ms.locfileid: "79467221"
---
# <a name="sample-c-project-for-code-analysis"></a>コード分析のためのサンプル C++ プロジェクト

次の手順では、 [「チュートリアル: CC++ /コードを分析して欠陥を分析](../code-quality/walkthrough-analyzing-c-cpp-code-for-defects.md)する」のサンプルを作成する方法について説明します。 この手順で次が作成されます。

- CppDemo という名前の Visual Studio。

- CodeDefects という名前のスタティック ライブラリ プロジェクト。

- Annotations という名前のスタティック ライブラリ プロジェクト。

この手順では、スタティック ライブラリのヘッダー ファイルと *.cpp* ファイルのコードも作成されます。

## <a name="create-the-cppdemo-solution-and-the-codedefects-project"></a>CppDemo ソリューションと CodeDefects プロジェクトを作成する

1. Visual Studio を開き、 **[新しいプロジェクトの作成]** を選択します。

1. 言語のフィルターを **C++** に変更します

1. **[空のプロジェクト]** を選択して **[次へ]** をクリックします

1. **[プロジェクト名]** テキスト ボックスに「**CodeDefects**」と入力します

1. **[ソリューション名]** テキスト ボックスに「**CppDemo**」と入力します

1. **[作成]**

## <a name="configure-the-codedefects-project-as-a-static-library"></a>CodeDefects プロジェクトをスタティック ライブラリとして構成する

1. ソリューション エクスプローラーで **[CodeDefects]** を右クリックし、 **[プロパティ]** をクリックします。

1. **[構成プロパティ]** を展開し、 **[全般]** をクリックします。

1. **[全般]** の一覧で、 **[構成の種類]** を **[スタティック ライブラリ (.lib)]** に変更します。

1. **[詳細]** の一覧で、 **[ターゲット ファイルの拡張子]** を **.lib** に変更します

## <a name="add-the-header-and-source-file-to-the-codedefects-project"></a>CodeDefects プロジェクトにヘッダーとソース ファイルを追加する

1. ソリューション エクスプローラーで **[CodeDefects]** を展開し、 **[ヘッダー ファイル]** を右クリックし、 **[追加]** をクリックし、 **[新しい項目]** をクリックします。

1. **[新しい項目の追加]** ダイアログ ボックスで、 **[コード]** をクリックし、 **[ヘッダー ファイル (.h)]** をクリックします。

1. **[名前]** ボックスに「**Bug.h**」と入力し、 **[追加]** をクリックします。

1. 次のコードをコピーし、エディターで *Bug.h* ファイルに貼り付けます。

    ```cpp
    #pragma once

    #include <windows.h>

    // These functions are consumed by the sample
    // but are not defined. This project cannot be linked!
    bool CheckDomain(LPCTSTR);
    HRESULT ReadUserAccount();

    // These constants define the common sizes of the
    // user account information throughout the program
    const int USER_ACCOUNT_LEN = 256;
    const int ACCOUNT_DOMAIN_LEN = 128;
    ```

1. ソリューション エクスプローラーで、 **[ソース ファイル]** を右クリックし、 **[新規作成]** をポイントし、 **[新しい項目]** をクリックします。

1. **[新しい項目の追加]** ダイアログ ボックスで、 **[C++ ファイル (.cpp)]** をクリックします。

1. **[名前]** ボックスに「**Bug.cpp**」と入力し、 **[追加]** をクリックします。

1. 次のコードをコピーし、エディターで *Bug.cpp* ファイルに貼り付けます。

    ```cpp
    #include "Bug.h"

    // the user account
    TCHAR g_userAccount[USER_ACCOUNT_LEN] = {};
    int len = 0;

    bool ProcessDomain()
    {
        TCHAR* domain = new TCHAR[ACCOUNT_DOMAIN_LEN];
        // ReadUserAccount gets a 'domain\user' input from
        //the user into the global 'g_userAccount'
        if (ReadUserAccount())
        {
            // Copies part of the string prior to the '\'
            // character onto the 'domain' buffer
            for (len = 0; (len < ACCOUNT_DOMAIN_LEN) && (g_userAccount[len] != L'\0'); len++)
            {
                if (g_userAccount[len] == '\\')
                {
                    // Stops copying on the domain and user separator ('\')
                    break;
                }
                domain[len] = g_userAccount[len];
            }
            if ((len = ACCOUNT_DOMAIN_LEN) || (g_userAccount[len] != '\\'))
            {
                // '\' was not found. Invalid domain\user string.
                delete[] domain;
                return false;
            }
            else
            {
                domain[len] = '\0';
            }
            // Process domain string
            bool result = CheckDomain(domain);

            delete[] domain;
            return result;
        }
        return false;
    }

    int path_dependent(int n)
    {
        int i;
        int j;
        if (n == 0)
            i = 1;
        else
            j = 1;
        return i + j;
    }
    ```

1. **[ファイル]** メニューをクリックし、 **[すべて保存]** をクリックします。

## <a name="add-the-annotations-project-and-configure-it-as-a-static-library"></a>Annotations プロジェクトを追加し、それをスタティック ライブラリとして構成する

1. ソリューション エクスプローラーで **[CppDemo]** をクリックし、 **[追加]** をポイントして **[新しいプロジェクト]** をクリックします。

1. **[新しいプロジェクトの追加]** ダイアログ ボックスで、言語のフィルターを **[C++]** に変更して **[空のプロジェクト]** を選択してから、 **[次へ]** をクリックします。

1. **[プロジェクト名]** テキスト ボックスに「**Annotations**」と入力し、 **[作成]** をクリックします。

1. ソリューション エクスプローラーで **Annotations** を右クリックし、 **[プロパティ]** をクリックします。

1. **[構成プロパティ]** を展開し、 **[全般]** をクリックします。

1. **[全般]** の一覧で、 **[構成の種類]** を変更し、 **[スタティック ライブラリ (.lib)]** をクリックします。

1. **[詳細]** の一覧で **[ターゲット ファイルの拡張子]** の隣にある列のテキストを選択し、「 **.lib**」と入力します。

## <a name="add-the-header-file-and-source-file-to-the-annotations-project"></a>ヘッダー ファイルとソース ファイルを注釈プロジェクトに追加する

1. ソリューション エクスプローラーで **[Annotations]** を展開し、 **[ヘッダー ファイル]** を右クリックし、 **[追加]** をクリックし、 **[新しい項目]** をクリックします。

1. **[新しい項目の追加]** ダイアログ ボックスで、 **[ヘッダー ファイル (.h)]** をクリックします。

1. **[名前]** テキスト ボックスに「**annotations.h**」と入力し、 **[追加]** をクリックします。

1. 次のコードをコピーし、エディターで *annotations.h* ファイルに貼り付けます。

    ```cpp
    #pragma once
    #include <sal.h>

    struct LinkedList
    {
        struct LinkedList* next;
        int data;
    };

    typedef struct LinkedList LinkedList;

    _Ret_maybenull_ LinkedList* AllocateNode();
    ```

1. ソリューション エクスプローラーで、 **[ソース ファイル]** を右クリックし、 **[新規作成]** をポイントし、 **[新しい項目]** をクリックします。

1. **[新しい項目の追加]** ダイアログ ボックスで、 **[コード]** をクリックし、 **[C++ ファイル (.cpp)]** をクリックします。

1. **[名前]** テキスト ボックスに「**annotations.cpp**」と入力し、 **[追加]** をクリックします。

1. 次のコードをコピーし、エディターで *annotations.cpp* ファイルに貼り付けます。

    ```cpp
    #include "annotations.h"

    LinkedList* AddTail(LinkedList* node, int value)
    {
        // finds the last node
        while (node->next != nullptr)
        {
            node = node->next;
        }

        // appends the new node
        LinkedList* newNode = AllocateNode();
        newNode->data = value;
        newNode->next = 0;
        node->next = newNode;

        return newNode;
    }
    ```

1. **[ファイル]** メニューをクリックし、 **[すべて保存]** をクリックします。

これでソリューションが完成し、エラーなしでビルドされるはずです。
