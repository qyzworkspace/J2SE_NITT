# J2SE_NITT
20180501

//在1-15之间选取5个不同的随机数

	static int[] ar = new int[5];

	public static void main(String[] args) {
		// 重复判断标记

		// 循环赋值
		for (int i = 0; i < ar.length; i++) {
			do {
				ar[i] = num();
			} while (isReapeat(i));
		}

		for (int i : ar) {
			System.out.println(i);
		}

	}

	// 随机数
	public static int num() {
		Random ran = new Random();
		int num = ran.nextInt(15) + 1;
		return num;
	}

	// 判断是否重复
	public static boolean isReapeat(int i) {
		boolean f = false;
		for (int j = 0; j < i; j++) {
			if (ar[j] == ar[i]) {
				return f = true;
			}
		}

		return f;
	}

	int[] ar1 = new int[5];

		int[] ar2 = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15 };
		// 产生一个随机数(1-15)，把它赋值给ar1，同时使ar2中的这个数的值为0
		// 第二次，产生一个随机数，遍历ar2比较，如果ar2[num]不为0，赋值给ar1，相同，
		// 继续产生新的，如此循环N次，直到ar2中有5个0；
		while (countZero(ar2) < 5) {
			int num = rd.nextInt(15) ;
			// 如果num与ar2中某个值相同，使ar2中的这个值等于0
			// 当ar2[num]不为0时，赋值给ar1[countZero(ar2)]
			
			if (ar2[num] != 0) {
				ar1[countZero(ar2)] = ar2[num];
				ar2[num] = 0;
			}
		}
    
    int[] ar = new int[5];
		// 一直遍历数组,存放数
		for (int i = 0; i < ar.length; i++) {
			// 取随机数
			int num = (int) (Math.random() * 15) + 1;
			// 判断，重复，就重新，不重复赋值
			boolean isReapeat = false;
			for (int j = 0; j < i; j++) {

				if (num == ar[j]) {
					isReapeat = true;
					break;
				}
			}
			//***利用 i-- 来控制语句
			if (isReapeat) {
				i--;
			} else {
				ar[i] = num;
			}
		}
