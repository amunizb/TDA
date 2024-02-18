import numpy as np

def low(a):
    '''
    Returns index of last non-zero element of an array a
    '''

    # Start checking from the end of the array
    for i in range(len(a)-1, -1, -1):
        if a[i] != 0:
            return i
    
    #If a = [0,...,0], return -1
    return -1

def transform_matrix(D):
    '''
    
    '''
    n = np.shape(D)[1]
    # Loop over columns
    for q in range(n):
        p = low(D[:, q])

        # Keep track if changed something
        modified = True
        
        while modified and p != -1:
            modified = False

            # Check if there is a previous column with same low
            for r in range(q):
                if low(D[:, r]) == p:
                    # Make a zero at D[p,q] and update p
                    D[:,q] = D[:,q] - D[p,q]/D[p,r] * D[:,r]
                    p = low(D[:, q])

                    modified = True

    return D
    


# Test function
# Create a randon matrix of size n x m
n = 7
m = 5
D = np.random.choice([0, 1, -1], size = (n, m))

print(f'Original matrix \n {D} \n')
print(f'Transformed matrix \n {transform_matrix(D)}')



