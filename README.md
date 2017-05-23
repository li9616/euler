# euler
A command line utility that converts euler angles to quaternions and rotation matrices. 

## Usage
```
$ euler [-r | --radians] [-i | --intrinsic | -e | --extrinsic]
        [-a | --active | -p | --passive] [-s S | --sequence=S]
        -- ANGLE ANGLE ANGLE

Calculates rotation matrix and quaternion for given Euler angle sequence.

Examples:
        euler -- 20 -10 35
        euler -ep -- 11.1 23.9 -129.4
        euler -ea -s yzy -- 41.2 -55.5 -97.8
        euler -p -s zxy -- -176.234 -0.231 44.399
        euler -rpi -s xzx -- 0.21 1.16 -2.81

    -h, --help
        Print help and exit
    -r, --radians
        Use radians instead of degrees for input angles (default: false)
    -i, --intrinsic
        Use intrinsic elemental rotations (incompatible with -e; default: true)
    -e, --extrinsic
        Use extrinsic elemental rotations (incompatible with -i; default: false)
    -a, --active
        Specify an active rotation (incompatible with -p; default: true)
    -p, --passive
        Specify a passive rotation (incompatible with -a; default: false)
    -s, --sequence
        The rotation sequence (possible values: xyz, xzy, yxz, yzx, zxy, zyx,
        xyx, xzx, yxy, yzy, zxz, zyz; default: xyz)
```

## Examples
```
$ euler -- 20 -10 35

Rotation Matrix:
  0.8067 -0.5649 -0.1736
  0.4903  0.8038 -0.3368
  0.3298  0.1866  0.9254

Quaternion:
 w:  0.9402
 x:  0.1392
 y: -0.1339
 z:  0.2806

$ euler -e -- 20 -10 35

Rotation Matrix:
  0.8067 -0.5876  0.0625
  0.5649  0.7357 -0.3738
  0.1736  0.3368  0.9254

Quaternion:
 w:  0.9311
 x:  0.1908
 y: -0.0298
 z:  0.3094

$ euler -ep -s yzy -- 11 -76 -143.2231

Rotation Matrix:
 -0.0760 -0.9525  0.2950
 -0.7772  0.2419  0.5809
 -0.6247 -0.1851 -0.7586

Quaternion:
 w:  0.3191
 x: -0.6002
 y:  0.7205
 z:  0.1373
```
